# 让 Agent 变得更强

这一阶段的目标是：让 Agent 不只是“能跑”，而是“开始有实际价值”。

## Memory：短期记忆与长期记忆

你需要区分：
- 短期记忆：当前会话上下文
- 长期记忆：跨会话持久信息
- 用户画像 / 偏好 / 环境信息
- 外部存储与内部上下文的边界

重点不是一开始就做复杂 memory 系统，而是理解：
- 什么信息值得记住
- 什么信息不应该记住
- Memory 如何影响稳定性与个性化

## RAG：让 Agent 接入外部知识

RAG 是很多 Agent 项目的基础能力。

你需要掌握：
- 文档切分、嵌入、召回的基本流程
- 如何把检索结果注入上下文
- 如何避免“检索了但没用上”
- 如何要求引用来源或 grounded output

建议至少完成一次：
- 本地文档知识库接入
- 查询 -> 检索 -> 总结 -> 引用来源 的完整闭环

## Planning：任务拆解与执行计划

当任务变长、多步、依赖复杂时，Agent 需要 planning。

你需要理解：
- 什么时候该显式规划
- 什么时候不该过度规划
- task decomposition 的基本形式
- planner-executor 结构
- 计划更新与中途修正

## Reflection / Review Loop

高质量 Agent 常常依赖 review loop。

你需要尝试：
- 自检输出是否满足格式和目标
- 二次审查结果是否合理
- 对工具执行结果进行 review
- 失败后重新规划或重试

注意：reflection 不是无限回环，而是受控的质量提升手段。

## Human-in-the-loop

真正能用于生产的 Agent，常常不能完全自动化。

你要理解：
- 哪些步骤必须让人确认
- 哪些步骤可以自动执行
- 如何设计 approve / reject / revise 的流程
- 如何在自动化和可控性之间平衡

## Checkpoint / Resume

长任务里，恢复能力很重要。

你应开始理解：
- 如何保存中间状态
- 如何恢复执行进度
- 如何记录运行上下文
- 如何避免中断后整个流程重来

## 阶段项目：Research Agent 或 Coding Assistant

建议第二个作品二选一：
- Research Agent：支持检索、整理、引用、结构化输出
- Coding Assistant：支持文件操作、计划、修改、审查、总结

## 这一章的完成标志

你应该能够：
- 把 memory / RAG / planning 接入真实项目
- 理解 Agent 的“持续执行”而不是单轮回答
- 拥有第二个更接近真实产品的作品

## 推荐资源

- Pinecone learn / RAG basics
  https://www.pinecone.io/learn/retrieval-augmented-generation/
- DSPy
  https://dspy.ai/
- LlamaIndex
  https://www.llamaindex.ai/
- LangChain memory / retrieval docs
  https://python.langchain.com/

建议：这一章最重要的不是收集名词，而是完成一次真实的“文档知识库 -> 检索 -> 引用输出”闭环。
