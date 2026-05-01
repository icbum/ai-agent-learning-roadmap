# Agent 心智模型

在学习任何框架前，先建立正确的 Agent 心智模型。否则很容易把“多轮 prompt + 几个 API 调用”误当成 Agent 工程。

## 什么是 AI Agent

Agent 不是“一个更长的 prompt”，而是一个能够在环境中感知、决策、调用工具、维护状态并持续执行任务的系统。

你至少要能区分：
- 一次性问答：用户提问，模型直接回答
- Workflow：预先定义好的步骤链路
- Agent：能够根据上下文和中间结果动态决定下一步行动

## Agent 的核心组成

一个最小 Agent 通常包含这些部分：
- Model：负责推理、判断、生成
- Tools：负责与外部世界交互
- State：保存当前任务上下文
- Memory：保留跨步骤或跨会话信息
- Planner / Policy：决定下一步如何行动
- Environment：Agent 操作的目标世界

这些部分不是必须全部复杂化，但你必须理解它们的职责边界。

## 什么场景适合 Agent

适合 Agent 的场景通常具备这些特点：
- 任务不是一步就能完成
- 中间可能需要调用工具
- 执行过程依赖环境反馈
- 任务目标明确，但过程不完全固定
- 需要在失败后重新尝试或调整路径

典型例子：
- Coding assistant
- Research agent
- Workflow automation
- Browser / terminal agent

## 什么场景不适合 Agent

有些任务根本不需要 Agent：
- 一次性固定格式生成
- 纯模板填充
- 完全确定的 ETL 流程
- 没有动态决策需求的脚本任务

很多时候，一个简单 workflow 比 agent 更稳定、更便宜、更可控。

## 从“调用模型”到“构建系统”的思维转变

真正的门槛不是会调用 API，而是开始思考：
- 状态怎么维护
- 工具怎么封装
- 失败怎么处理
- 结果怎么评估
- 成本怎么控制
- 系统怎么部署和演进

从这一刻开始，你学的就不是“模型应用小技巧”，而是 Agent 工程。

## 这一章的完成标志

你应该能够：
- 用自己的话解释 Agent 的定义
- 区分 assistant、workflow、agent
- 画出一个最小 Agent 架构图
- 解释什么任务值得用 Agent，什么不值得

## 推荐资源

- Anthropic: Building effective agents
  https://www.anthropic.com/engineering/building-effective-agents
- OpenAI Guides / Function calling / Structured outputs
  https://platform.openai.com/docs/guides/function-calling
  https://platform.openai.com/docs/guides/structured-outputs
- LangGraph conceptual guides
  https://langchain-ai.github.io/langgraph/

建议：这一章看资料的目标不是背定义，而是把最小 Agent 架构图画出来。
