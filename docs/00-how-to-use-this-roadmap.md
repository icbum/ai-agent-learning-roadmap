# 如何使用这份路线图

这份路线图面向已经具备 Python、API 调用、Linux/终端基础，并希望进入 AI Agent 工程岗位的开发者。

## 目标

这套 docs 的目标不是让你“看过很多 Agent 概念”，而是让你逐步形成下面这些能力：
- 能自己写出单 Agent + tool calling 系统
- 能接入 memory、RAG、planning、review loop
- 能理解多 Agent / workflow 编排
- 能把 Agent 系统做成可评估、可部署、可展示的工程项目
- 能把这些能力转化成 GitHub 作品集和求职竞争力

## 推荐阅读顺序

1. 先读 [01-Agent 心智模型](01-agent-mental-model.md)
2. 再读 [02-构建你的第一个可用 Agent](02-build-your-first-agent.md)
3. 然后读 [03-让 Agent 变得更强](03-enhance-agent-capabilities.md)
4. 接着读 [04-从单 Agent 到 Agent System](04-agent-systems.md)
5. 再读 [05-生产化能力](05-production-readiness.md)
6. 最后结合 [06-生态与工具地图](06-ecosystem-and-tools.md)、[07-求职与作品集](07-job-search-and-portfolio.md)、[08-12 周学习计划](08-12-week-plan.md)

## 学习方法建议

### 1. 以项目为中心

每一阶段都应该有一个对应的项目产出，而不是只做笔记。建议至少完成：
- 一个 CLI Tool-Using Agent
- 一个 Research / RAG Agent
- 一个 Coding / Workflow Agent
- 一个 Production-Style Agent System

### 2. 每学一个能力都要沉淀文档

建议你持续记录：
- 为什么采用这种架构
- 哪些地方踩过坑
- 如何评估效果
- 有哪些已知限制

这些内容最后都会变成 README、博客、面试表达和作品集素材。

### 3. 优先理解底层能力，而不是只学框架

学习 LangGraph、MCP、Hermes、Claude Code、OpenClaw 之前，先确认你真的理解：
- tool calling
- state management
- memory
- planning
- review loop
- orchestration

## 这份路线图不重点覆盖什么

为了保证这份 roadmap 聚焦工程落地，它不会把大量篇幅放在：
- 纯理论 LLM 研究
- 只讲 prompt engineering 的技巧汇总
- 单一框架的 API 使用手册
- 与求职和工程落地关系较弱的学术细枝末节

## 判断自己有没有真正学会

每个阶段结束时，问自己这三个问题：
- 我能不能把这个能力做成一个独立项目？
- 我能不能把设计取舍讲清楚？
- 我能不能把它写进 README 或简历？

如果不能，说明还没有真正掌握。

## 推荐资源

### 官方文档优先
- OpenAI Platform Docs: https://platform.openai.com/docs
- Anthropic Docs: https://docs.anthropic.com/
- Model Context Protocol: https://modelcontextprotocol.io/

### 代码与系统优先
- Hermes Agent: https://github.com/NousResearch/hermes-agent
- OpenClaw: https://github.com/edmundpf/openclaw
- LangGraph: https://github.com/langchain-ai/langgraph

### 学习建议
- 先看官方能力说明，再看示例代码
- 看完概念后马上自己实现一个最小版本
- 不要只收藏资源，必须配套项目练习
