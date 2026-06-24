# 前端开发学习路线与核心概念

前端开发是构建 Web 应用程序用户界面（UI）和用户体验（UX）的过程。现代前端已从简单的 HTML/CSS/JS 演变为复杂的单页应用（SPA）和组件化架构。

## 1. 核心基石

### HTML5 & CSS3
*   **语义化 HTML**：使用 `<header>`, `<nav>`, `<article>`, `<section>`, `<footer>` 等标签，有利于 SEO 和无障碍访问（Accessibility）。
*   **现代 CSS 布局**：
    *   **Flexbox (弹性盒布局)**：主要用于一维布局（行或列）。
    *   **Grid (网格布局)**：用于二维布局（同时处理行和列）。
*   **CSS 变量 (Custom Properties)**：用于构建动态主题（如暗黑模式）。
    ```css
    :root {
      --primary-color: #3b82f6;
    }
    ```

### JavaScript (ES6+)
JavaScript 是前端的灵魂。现代前端开发必须掌握 ES6+ 的核心特性：
*   **解构赋值**、**箭头函数**、**模板字符串**。
*   **异步编程**：理解 Event Loop（事件循环）、Promise、`async/await`。
*   **模块化 (ES Modules)**：使用 `import` 和 `export` 组织代码。

---

## 2. 现代前端框架

现代主流前端框架（React, Vue, Angular）均基于**组件化**和**声明式渲染**的思想。

### React
*   **声明式 (Declarative)**：React 使创建交互式 UI 变得轻而易举。为你程序中的每个状态设计简明的视图，当数据改变时 React 能有效地更新并渲染。
*   **JSX**：JavaScript 的语法扩展，允许在 JS 中直接编写类似 HTML 的结构。
*   **Hooks 状态管理**：
    *   `useState`：管理组件本地状态。
    *   `useEffect`：处理副作用（如数据请求、订阅等）。
*   **虚拟 DOM (Virtual DOM)**：React 在内存中维护一个虚拟 DOM 树，通过 Diff 算法计算出最小的变化，然后一次性更新到真实 DOM，提高渲染性能。

---

## 3. 构建工具与工作流

由于现代前端代码需要进行类型检查、压缩、打包、向下兼容转换，构建工具不可或缺。

*   **Vite**：目前最受欢迎的新一代构建工具。利用浏览器原生的 ES 模块（ESM）支持，在开发阶段实现极快的冷启动和热更新（HMR）。
*   **npm / pnpm / yarn**：包管理器，用于管理项目依赖。`pnpm` 通过硬链接机制大幅节省磁盘空间并提高安装速度。
*   **TypeScript**：JavaScript 的超集，引入了静态类型检查，极大提升了大中型项目代码的健壮性和可维护性。

<!-- recompile trigger -->
