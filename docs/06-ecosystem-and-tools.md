# 生态与工具地图

这一章不是为了追新，而是为了建立工具坐标系。

## 模型接口层

优先理解：
- OpenAI 风格 tool calling
- Anthropic 风格工具使用
- 结构化输出与 schema 约束

这是所有上层系统的基础。

## Agent 编排层

可以按“理解思路”的方式学习：
- LangGraph：更偏 workflow / state graph
- AutoGen：多 Agent 对话与协作
- CrewAI：角色化 Agent 工作流

目标不是全都精通，而是知道它们各自想解决什么问题。

## 协议与集成层：MCP

MCP 很值得学，因为它直接关系到 Agent 如何接入外部工具生态。

你需要理解：
- MCP 解决的核心问题是什么
- 工具暴露和调用的边界在哪里
- 为什么 MCP 会成为很多 Agent 系统的重要集成方式

## 实战型 Agent 系统

建议重点研究：
- Hermes
- Claude Code
- OpenClaw

研究方式不是“当普通用户使用”，而是观察：
- 它们如何组织 prompt、toolsets、memory、session、workflow
- 它们如何处理长任务、中断恢复、多工具执行
- 它们如何向工程系统演进

## 对框架的基本态度

尽量避免一个误区：
“把学会某个框架，误认为学会了 Agent 工程。”

更健康的顺序是：
- 先理解核心能力
- 再学框架如何封装这些能力
- 最后根据场景选型

## 这一章的完成标志

你应该能够：
- 说清主要 Agent 框架和系统分别在解决什么问题
- 判断一个工具更适合 workflow、单 Agent 还是多 Agent
- 把 Hermes、Claude Code、OpenClaw 放到正确的工程语境里理解

## 推荐资源

- Model Context Protocol
  https://modelcontextprotocol.io/
- Claude Code docs
  https://docs.anthropic.com/en/docs/claude-code/overview
- Hermes Agent repo
  https://github.com/NousResearch/hermes-agent
- OpenClaw repo
  https://github.com/edmundpf/openclaw

建议：这一章的任务不是“学会所有工具”，而是建立一张自己的 Agent 生态地图。
