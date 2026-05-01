# AI Agent应用学习路线

面向具备 Python、API 调用、Linux/终端基础，并希望进入 AI Agent 工程岗位的开发者。

## 如何使用这份路线图

这份仓库已经从单文件 roadmap 拆分为 docs 结构，建议按下面顺序阅读：

1. [00-如何使用这份路线图](docs/00-how-to-use-this-roadmap.md)
2. [01-Agent 心智模型](docs/01-agent-mental-model.md)
3. [02-构建你的第一个可用 Agent](docs/02-build-your-first-agent.md)
4. [03-让 Agent 变得更强](docs/03-enhance-agent-capabilities.md)
5. [04-从单 Agent 到 Agent System](docs/04-agent-systems.md)
6. [05-生产化能力](docs/05-production-readiness.md)
7. [06-生态与工具地图](docs/06-ecosystem-and-tools.md)
8. [07-求职与作品集](docs/07-job-search-and-portfolio.md)
9. [08-12 周学习计划](docs/08-12-week-plan.md)

## 项目模板

如果你想直接把学习路线变成作品集，可以按这个顺序做项目：

1. [CLI Tool-Using Agent](projects/01-cli-tool-using-agent.md)
2. [Research / RAG Agent](projects/02-research-rag-agent.md)
3. [Coding / Workflow Agent](projects/03-coding-workflow-agent.md)
4. [Production-Style Agent System](projects/04-production-style-agent-system.md)

项目模板总览：
- [projects/README.md](projects/README.md)

## 你会获得什么

完成这条路线后，你应该能够：
- 独立构建一个支持工具调用的单 Agent 系统
- 为 Agent 接入 memory、RAG、planning、review loop 等能力
- 设计基础的多 Agent / workflow 架构
- 为 Agent 系统补齐日志、评估、配置、重试、权限边界等生产能力
- 看懂并上手 Hermes、Claude Code、OpenClaw、MCP 等相关生态
- 产出可用于求职的 GitHub 项目与作品集

## 仓库结构

```text
docs/
├── 00-how-to-use-this-roadmap.md
├── 01-agent-mental-model.md
├── 02-build-your-first-agent.md
├── 03-enhance-agent-capabilities.md
├── 04-agent-systems.md
├── 05-production-readiness.md
├── 06-ecosystem-and-tools.md
├── 07-job-search-and-portfolio.md
└── 08-12-week-plan.md

projects/
├── README.md
├── 01-cli-tool-using-agent.md
├── 02-research-rag-agent.md
├── 03-coding-workflow-agent.md
└── 04-production-style-agent-system.md
```

## 适合谁

这份路线图适合：
- 会使用 Python 进行日常开发
- 理解 HTTP / API 调用、JSON、认证等基本概念
- 能在 Linux / WSL / macOS 终端中完成常见开发操作
- 希望进入以 AI Agent、LLM 应用、自动化智能体、Agent System 为方向的工程岗位

这份路线图不面向完全零基础编程新手，也不以纯理论研究为核心目标。重点是：构建真正可运行、可评估、可部署、可展示的 Agent 工程能力。
