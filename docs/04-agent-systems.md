# 从单 Agent 到 Agent System

这一阶段的目标是：理解更复杂的系统组织方式，而不是只会一个单循环 Agent。

## 为什么需要多 Agent

不是所有问题都需要多 Agent。你要先搞清楚：
- 多 Agent 真正解决了什么问题
- 它适合并行拆分、角色分工、复杂工作流还是组织隔离
- 什么时候多 Agent 只是增加复杂度

## 常见多 Agent 模式

建议重点掌握这几类：
- Router：根据任务路由到不同能力单元
- Planner / Executor：一个负责规划，一个负责执行
- Manager / Worker：一个负责拆任务，多个执行子任务
- Reviewer / Critic：一个生成，一个审查

你不需要一开始就把模式做得很复杂，但要能理解不同模式的职责边界。

## Shared State 与消息传递

多 Agent 系统的难点不只是“多开几个模型调用”，而是：
- 状态怎么共享
- 上下文怎么隔离
- 任务边界如何定义
- 结果如何汇总
- 失败如何回滚或重试

## 并发与结果聚合

你要开始思考更真实的工程问题：
- 哪些任务可以并发
- 哪些步骤必须串行
- 如何聚合多个子结果
- 如何避免上下文爆炸
- 如何做 timeout / cancellation

## 结合代表性系统理解设计

在这一阶段，你可以开始系统性观察：
- Hermes：工具系统、技能、记忆、delegation、cron、gateway
- Claude Code：编码任务循环、工具调用、代码工作流
- OpenClaw：代理式代码与任务执行范式

重点不是“会用产品”，而是理解这些系统背后的工程抽象。

## 阶段项目：Multi-Agent Workflow

建议第三个作品：
- 拥有 router 或 manager-worker 结构
- 支持多个子任务协同
- 支持状态记录与结果聚合
- 有失败处理与基本可观测能力

## 这一章的完成标志

你应该能够：
- 知道什么时候该用多 Agent，什么时候不该用
- 实现一个基本的 orchestrated workflow
- 解释 Hermes / Claude Code / OpenClaw 一类系统的关键设计思路

## 推荐资源

- LangGraph docs
  https://langchain-ai.github.io/langgraph/
- Microsoft AutoGen
  https://microsoft.github.io/autogen/
- CrewAI docs
  https://docs.crewai.com/
- Hermes Agent repo
  https://github.com/NousResearch/hermes-agent

建议：这一章不要只看框架 API，重点看任务边界、状态流动和失败恢复。
