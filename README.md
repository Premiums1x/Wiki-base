# 💻 Computer Science Knowledge Base (my-wiki)

这是一个基于 `sage-wiki` (Graph-RAG 知识库系统) 构建的计算机科学多维度知识库项目。本项目通过 9 份核心路线图文档作为示例，通过sage-wiki自动编译并关联出 101 个核心概念以及 46 条强类型本体关系线。

---

## 🛠️ 项目定制与改动说明

为了适配 SiliconFlow (硅基流动) API、优化关系图谱的可视化效果、以及更好地兼容 Obsidian，本项目进行了以下核心优化：

### 1. ✍️ 优化原始 Prompt（解决图谱无连线问题）
- **问题背景**：默认的写作提示词仅引导 LLM 在最底部的 `## See also` 部分罗列 `[[wikilinks]]`。这导致 `sage-wiki` 的关系提取器因为检测不到共现的关系动词（如 `extends`, `implements`），无法在 SQLite 中生成连线（Edges 为 0），从而导致 Web UI 图谱空白。
- **改动方案**：在项目根目录下新建 `prompts/write-article.md` 自定义模板，在原有模板基础上引入了 **关系词引导演算法规**：
  > [!IMPORTANT]
  > 强制 LLM 必须在正文（如 Definition 或 How it works）中提及相关概念，并且必须使用强关系词搭配双括号链接。例如：
  > * `The Transformer [[extends]] [[deep-learning]]...`
  > * `Kubernetes [[implements]] [[docker]]...`
- **成效**：重新编译后，数据库关系连线从 **0 条爆发增长至 46 条**，Web 端的力导向图谱完整连通。

#### 编译成功启动sage-wiki的web端效果：
![image](../my-wiki/assets/image.png)

### 2. ⚙️ 配置模型与 API Key（优化响应速度与稳定性）
- **安全配置**：配置 `config.yaml` 动态读取系统级环境变量 `${SILICONFLOW_API_KEY}`，避免 API 密钥硬编码泄露。
- **模型分流调优 (Model Split)**：
  为了规避 SiliconFlow 大模型高峰期拥堵超时（120秒 Client.Timeout）及小模型生成 JSON 格式损坏的问题，对任务链进行了精细化模型分配：
  - **`summarize` (摘要)**、**`lint` (检查)**、**`query` (检索)**：采用超高速的 `Qwen/Qwen2.5-7B-Instruct`，毫秒级响应。
  - **`extract` (概念提取)**：升级为中等体量、逻辑稳定的 `Qwen/Qwen2.5-14B-Instruct`，彻底解决 7B 模型输出非标准 JSON 的解析异常。
  - **`write` (写作)**：使用 `Qwen/Qwen2.5-14B-Instruct`，保证输出高质量、带逻辑的 markdown 页面。
- **扩展嵌入模型窗口**：
  - 将默认嵌入模型重写为 `BAAI/bge-m3`，将 token 上限提升至 **8,192**，完美兼容超长的原始计算机路线图输入。

### 3. 📂 修改 Obsidian 相关配置
- **双轨图谱共存**：
  - 本项目初始化了 `.obsidian` 配置目录，使其能够作为 **Obsidian 库 (Vault)** 正常打开。
  - **扁平引用与本体逻辑的互补**：
    - **Obsidian 关系图**：展示只要有 `[[链接]]` 就会连线的**非结构化交叉引用网**（适合散点发散思维）。
    - **sage-wiki Web 关系图**：只展示经过严格动词筛选的**本体逻辑关联网**（如继承、依赖、权衡，适合结构化深度检索）。

---

## 🚀 快速启动指南

### 1. 启动 Web 交互界面
如果你想在本地浏览器中查看带动态 3D/2D 力导向图的网页，直接运行：
```powershell
$env:SILICONFLOW_API_KEY = [System.Environment]::GetEnvironmentVariable("SILICONFLOW_API_KEY","User")
E:\project\Lan\sage-wiki\sage-wiki.exe serve --ui
```
打开浏览器访问：[http://127.0.0.1:3333](http://127.0.0.1:3333)

### 2. 增量编译 (当 raw/ 目录下文档发生修改时)
编译命令会自动比对文件哈希，只处理修改过的文件（增量更新）：
```powershell
E:\project\Lan\sage-wiki\sage-wiki.exe compile
```

### 3. Claude Code 全局 MCP 接入
你可以通过以下命令将 `sage-wiki` 注册到 Claude Code 中（注意替换为你的实际路径），实现全局任意终端访问知识库：

```powershell
claude mcp add sage-wiki "E:\project\Lan\sage-wiki\sage-wiki.exe" mcp --dir "E:\project\Lan\my-wiki" -s user
```

配置完成后，在任意终端运行 `claude` 即可调用以下专属工具：
- `wiki_search` (混合搜索知识库)
- `wiki_ontology_query` (以某个概念出发查询上下级关联节点)
- `wiki_capture` (一键将当前的对话发现写入本地知识库)
