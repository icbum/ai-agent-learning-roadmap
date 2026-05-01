# 构建你的第一个可用 Agent

这一阶段的目标是：从“会调模型”进化到“能做一个真正可运行的单 Agent”。

## 模型调用与结构化输出

你需要熟练掌握：
- Chat Completions / Responses 类接口的基本使用
- system / user / assistant message 结构
- temperature、max tokens、上下文长度等常见参数
- JSON / schema / structured output 的约束方式

你不需要一开始就深入所有 provider 差异，但必须能稳定完成：
- 调用模型
- 解析结构化结果
- 对失败结果做基本兜底

## Tool Calling / Function Calling

这是进入 Agent 工程的第一道门槛。

你需要学会：
- 定义 tool schema
- 让模型选择工具
- 执行工具并把结果回填给模型
- 处理工具错误、超时、空结果和异常返回

建议先实现几类基础工具：
- 文件读写
- Shell 命令执行
- Web 搜索 / 页面提取
- 简单计算或数据处理

## Agent Loop 与状态管理

一个最小可用 Agent 至少需要：
- 接收任务输入
- 循环调用模型
- 识别是否需要工具调用
- 执行工具
- 把结果回送模型
- 在满足条件后结束

你还需要理解：
- 如何设置最大迭代次数
- 如何定义停止条件
- 如何保存中间状态
- 如何防止无限循环

## Prompt 设计与任务约束

Agent 场景下，prompt 重点不是花哨，而是：
- 角色边界
- 任务目标
- 工具使用规范
- 输出格式约束
- 错误处理策略
- 成功标准定义

你要学会把 prompt 写成“可执行说明”。

## 错误处理、重试与日志

很多 demo 能跑，但不稳定。工程上至少要补齐：
- API 重试
- 工具失败重试
- 超时控制
- 运行日志
- 中间步骤记录
- 基础调试信息

## 阶段项目：CLI Tool-Using Agent

建议完成第一个作品：
- 一个命令行 Agent
- 支持至少 3 类工具
- 能显示每一步执行过程
- 能处理常见失败情况
- 有清晰 README

## 这一章的完成标志

你应该能够：
- 从零写出单 Agent loop
- 理解 tool calling 的完整闭环
- 做出一个可运行的 CLI Agent 项目

## 推荐资源

- OpenAI function calling docs
  https://platform.openai.com/docs/guides/function-calling
- Anthropic tool use docs
  https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview
- PydanticAI
  https://ai.pydantic.dev/
- Instructor
  https://python.useinstructor.com/

建议：这一章边看边写，不要只读文档。最有效的练习是手写一个支持工具调用的 CLI Agent。
