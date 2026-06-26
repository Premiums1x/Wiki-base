# 异步并发任务队列 (AsyncTaskQueue) 设计与实现案例分析

## 背景与问题描述

在前端面试或实际系统设计（如网络请求调度、资源加载限制）中，设计一个限制最大并发数的异步任务队列是一个经典问题。

### 问题定义
实现一个 `AsyncTaskQueue` 类，用于管理异步任务的执行，满足以下要求：
1. **并发控制**：保证同时运行的任务数不超过指定的 `concurrency` 限制。
2. **先进先出 (FIFO)**：任务按被添加的顺序依次执行。
3. **静默忽略失败**：若某个任务的 Promise 被 reject，静默忽略该错误，且不影响队列中后续任务的执行。

---

## 迭代与调试历程

本篇记录了从最初的探索到最终优雅实现的完整调试与迭代过程。

### 阶段一：初步探索与关键遗漏（版本 1）

#### 初始代码
```typescript
class AsyncTaskQueue {
    concurrency: any;
    posts: Promise<void>[] = [];
    constructor(concurrency: number) {
        this.concurrency = concurrency
    }
    queue(task: () => Promise<void>) {
        if(this.posts.length < this.concurrency ){
            try {
                task();
            }catch{
                
            }
        }
    }
}
```

#### 存在的主要漏洞
1. **缺少等待队列**：当运行中的任务数达到并发上限时，新来的任务被直接丢弃，没有排队等待的机制。
2. **并发计数失效**：虽然声明了 `posts` 数组，但执行 `task()` 后并没有将返回的 Promise 放入数组中，导致 `this.posts.length` 永远为 `0`。
3. **无法捕获 Promise Rejection**：同步的 `try...catch` 块无法捕获 `task()` 返回的异步 Promise 的拒绝事件，导致未捕获的 Promise 错误。

---

### 阶段二：架构重构与细节硬伤（版本 2）

为了解决排队和异步控制问题，采用了“等待队列 + 计数器 + 递归驱动”的优秀架构，但引入了几个经典语法和边界 Bug。

#### 迭代代码
```typescript
class AsyncTaskQueue {
    private concurrency: number;
    private waitingQueque: (()=>Promise<any>)[];
    private taskCounting:number;
    constructor(concurrency) {
        this.concurrency = concurrency;
    };

    queue(task) {
        waitingQueque.push(task);
        if( waitingQueque.length != 0 && taskCounting < this.concurrency){
            watingQueque.length-1;
            taskCounting++;
            tryStart();
        }
    }    
}
tryStart (){
    const nextQueque = this.waitingQueque.shift();
    nextQueque()
        .catch()
        .finally({
            this.taskCounting--; 
            tryStart();
        })  
}
```

#### 引入的新问题
1. **作用域与 `this` 缺失**：在类的方法中访问属性或调用其他方法时漏掉了 `this.`，如 `waitingQueque`、`tryStart()`。
2. **属性未初始化**：`waitingQueque` 和 `taskCounting` 声明了类型但未赋初值，运行时值为 `undefined`，直接调用 `push` 或递增会报错。
3. **方法越界**：`tryStart` 写在了类的大括号外部，变成了全局函数。
4. **`.finally()` 语法错误**：`.finally()` 接收的必须是回调函数，而此处写成了普通代码块大括号。
5. **修改 `length` 导致任务丢失**：代码中有一处 `watingQueque.length-1`（或后来的 `length--`），直接修改数组长度会导致刚刚 push 进去的任务被物理截断删除。

---

### 阶段三：逻辑跑通与边界防范（版本 3）

修正了大部分语法和作用域问题后，开始处理空队列判断和计数器数值同步问题。

#### 迭代代码
```typescript
class AsyncTaskQueue {
    private concurrency: number;
    private waitingQueue: (()=>Promise<any>)[] = [];
    private taskCounting:number = 0 ;
    constructor(concurrency) {
        this.concurrency = concurrency;
    };

    queue(task) {
        this.waitingQueue.push(task);
        if( this.waitingQueue.length != 0 && this.taskCounting < this.concurrency){
            this.tryStart();
        }
    }   
    tryStart (){
        if (this.waitingQueue.length === 0) return;
        this.taskCounting++;
        const nextQueue = this.waitingQueue.shift();
        nextQueue()
            .catch(()=>{})
            .finally(()=>{
                this.taskCounting--; 
                this.tryStart();
            })  
    }
}
```

#### 逻辑运行分析
该版本成功跑通了核心流程。
* 任务放入队列后，由 `queue` 进行前置并发数判定并启动 `tryStart`。
* `tryStart` 内部包含 `length === 0` 的安全守卫，避免了对 `undefined` 的调用。
* 在 `finally` 回调中将计数器递减，并递归调用 `tryStart` 驱动下一个任务。

---

### 阶段四：终极优化与卫语句模式（版本 4）

为了使代码更加健壮和符合单一职责原则，我们可以将所有的状态校验（并发数、队列状态）收拢到 `tryStart` 的入口处。

#### 终极优化代码
```typescript
class AsyncTaskQueue {
    private concurrency: number;
    private waitingQueue: (() => Promise<any>)[] = [];
    private taskCounting: number = 0;

    constructor(concurrency: number) {
        this.concurrency = concurrency;
    }

    queue(task: () => Promise<any>): void {
        // 1. 职责单一：只负责入队和触发启动
        this.waitingQueue.push(task);
        this.tryStart();
    }   

    private tryStart(): void {
        // 2. 统一的安全网与准入阀门（卫语句模式）
        if (this.taskCounting >= this.concurrency || this.waitingQueue.length === 0) {
            return;
        }

        const nextTask = this.waitingQueue.shift();
        if (!nextTask) return; // 严格模式空安全守卫

        this.taskCounting++; // 任务确立启动，计数器加 1

        nextTask()
            .catch(() => {
                // 3. 静默忽略任何异常，防止未捕获的 rejection 导致崩溃
            })
            .finally(() => {
                this.taskCounting--; // 任务结束，释放名额
                this.tryStart();     // 递归尝试启动下一个任务
            });
    }
}
```

---

## 核心技术沉淀与 Gotchas

### 1. 数组长度截断风险
在 JavaScript 中，修改数组的 `length` 属性是具有破坏性的：
* `arr.length--` 会直接将数组的最后一个元素删除。
* 队列的元素消费应该完全由 `shift()` 等标准方法负责，绝不能手动修改 `length`。

### 2. 异步 Rejection 捕获
普通的 `try...catch` 只能捕获当前调用栈内的同步异常。对于返回 Promise 的异步任务：
* 必须在 Promise 链上挂载 `.catch(() => {})`。
* 或者在 `async` 函数中使用 `await` 配合 `try...catch`。

### 3. 并发计数器的生命周期同步
并发计数器（如 `taskCounting`）的增减必须与任务的生命周期高度绑定：
* **递增时机**：必须在任务出队并即将执行（即 `nextTask()` 调用前）时立刻递增。
* **递减时机**：必须在 `.finally()` 中递减，确保无论任务是 resolve 还是 reject 都能释放名额。
* **准入把关**：将并发条件检测（`taskCounting >= concurrency`）统一写在递归入口的最前端，可以避免在多个触发源（如 `queue` 和 `finally`）重复编写判断代码，防止计数器与实际运行任务数脱节。
