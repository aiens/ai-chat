# 甜云AI超级助手



<p align="center">
  <strong>功能强大、易于部署的新一代AI对话助手</strong>
</p>

<p align="center">
  <a href="#主要特性">主要特性</a> •
  <a href="#快速开始">快速开始</a> •
  <a href="#部署指南">部署指南</a> •
  <a href="#系统架构">系统架构</a> •
  <a href="#技术栈">技术栈</a> •
  <a href="#路线图">路线图</a> •
  <a href="#贡献指南">贡献指南</a> •
  <a href="#许可证">许可证</a>
</p>

## 主要特性

甜云AI超级助手是增强版AI对话系统，专注于提供流畅的本地与云端AI模型体验。

### 💡 核心优势

- **多模型支持**：同时支持DeepSeek、OpenAI、Anthropic、Gemini等云端模型和Ollama本地模型
- **知识库增强**：强大的文档处理和向量检索系统，让AI能够基于您的文档回答问题
- **记忆库功能**：智能记忆管理，使AI助手能够记住您的偏好和过往对话
- **联网搜索**：实时获取最新信息，告别知识截止日期的限制
- **简易部署**：提供Docker一键部署、桌面应用和云服务快速部署多种选择
- **数据隐私**：支持完全本地部署，数据存储在您自己的设备或服务器上

### 🔄 本地/云端无缝切换

- 根据需求在云端模型和本地模型之间轻松切换
- 灵活选择数据存储位置，满足不同隐私需求
- 支持数据导入/导出和同步功能

### 🧩 插件生态系统

- 丰富的内置插件：文件处理、代码执行、图表生成等
- 可扩展的插件架构，支持社区开发和贡献
- 标准化的插件接口，简化新功能开发

## 快速开始

### 使用Docker快速部署

```bash
# 克隆仓库
git clone https://github.com/aiens/ai-chat.git
cd ai-chat

# 启动服务
docker-compose up -d
```

访问 `http://localhost:3000` 开始使用甜云AI超级助手。

### 桌面应用安装

从[发布页面](https://github.com/sweet-cloud/ai-assistant/releases)下载适合您系统的安装包：
- Windows (.exe)
- macOS (.dmg)
- Linux (.AppImage)

### 云端一键部署

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fsweet-cloud%2Fai-assistant)

## 部署指南

### Docker部署详细步骤

1. 确保已安装Docker和Docker Compose
2. 克隆仓库并进入项目目录
3. 复制环境变量示例文件：`cp .env.example .env`
4. 编辑`.env`文件，配置必要的API密钥和设置
5. 启动服务：`docker-compose up -d`

### 开发环境设置

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build
```

### 本地模型配置

甜云AI超级助手原生支持[Ollama](https://ollama.ai/)本地模型：

1. 安装并启动Ollama
2. 在甜云AI设置中选择"本地模型"
3. 配置Ollama API端点（默认为`http://localhost:11434`）
4. 选择您想使用的模型（如Llama 3、Mistral等）

## 系统架构

甜云AI超级助手采用模块化架构设计，确保系统的可扩展性和灵活性：

```
+---------------------+
|    用户界面层       |
|  (Next.js + React)  |
+----------+----------+
           |
+----------v----------+
|    应用服务层       |
| (会话管理、插件系统) |
+----------+----------+
           |
+----------v----------+       +---------------+
|     AI服务层        | <---> |   本地模型    |
| (模型适配与通信)     |       | (Ollama)     |
+----------+----------+       +---------------+
           |                          
           |                  +---------------+
           +----------------> |   云端模型    |
                             | (OpenAI等API) |
+----------+----------+       +---------------+
|    数据存储层       |
| (本地/云端数据库)   |
+----------+----------+
           |
+----------v----------+
|    知识/记忆库      |
|  (向量数据库)      |
+---------------------+
```

### 核心组件

- **用户界面层**：基于Next.js和React的响应式前端
- **应用服务层**：处理业务逻辑、会话管理和插件集成
- **AI服务层**：负责与不同AI模型提供商的通信
- **数据存储层**：管理对话历史、用户设置和知识库数据
- **插件系统**：提供功能扩展能力

## 技术栈

### 前端技术
- Next.js 14 (App Router)
- React 18
- TailwindCSS
- Zustand (状态管理)
- Radix UI (UI组件库)
- ShadcnUI (UI组件主题)

### 后端技术
- Node.js
- Prisma ORM (数据库访问)
- PostgreSQL/SQLite (数据存储)
- Ollama API (本地模型集成)
- OpenAI、Anthropic、Gemini等API集成

### 部署技术
- Docker & Docker Compose
- Vercel (云端快速部署)
- Supabase (可选云数据库服务)

### 知识库技术
- LangChain (向量检索)
- ChromaDB (向量数据库)
- Unstructured (文档解析)

## 路线图

### 已完成
- [x] 基础系统搭建
- [x] 多模型支持
- [x] 基础知识库功能
- [x] Docker部署支持

### 进行中
- [ ] Ollama本地模型集成优化
- [ ] 知识库和记忆库增强
- [ ] 桌面应用开发
- [ ] 联网搜索插件完善

### 计划中
- [ ] 移动设备体验优化
- [ ] 高级插件系统
- [ ] 数据同步机制
- [ ] 社区插件市场

## 贡献指南

我们欢迎社区贡献，无论是功能开发、文档改进还是问题反馈：

1. Fork本仓库
2. 创建您的特性分支：`git checkout -b feature/amazing-feature`
3. 提交您的更改：`git commit -m '添加一些特性'`
4. 推送到分支：`git push origin feature/amazing-feature`
5. 提交Pull Request

请确保遵循我们的[行为准则](CODE_OF_CONDUCT.md)和[贡献指南](CONTRIBUTING.md)。

## 许可证

本项目采用MIT许可证 - 详见[LICENSE](LICENSE)文件。

## 致谢

- [LobeChat](https://github.com/lobehub/lobe-chat) - 提供了强大的基础架构
- [Ollama](https://github.com/ollama/ollama) - 优秀的本地模型运行环境
- [LangChain](https://github.com/hwchase17/langchainjs) - 强大的AI应用框架
- 以及所有贡献者和社区支持者！

---

<p align="center">由 ❤️ 和 ☕ 驱动</p>
<p align="center">© 2025 甜云科技</p>
