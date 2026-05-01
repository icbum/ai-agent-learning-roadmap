# CLI Tool-Using Agent

## 项目目标

构建一个命令行 AI Agent，能够根据用户任务调用多个工具完成实际工作。

## 这个项目要证明什么

它主要证明你具备：
- 单 Agent loop 设计能力
- tool calling / function calling 能力
- 工具执行与结果回填能力
- 基础日志、重试、错误处理能力

## 最小功能范围

建议至少支持：
- 文件读写工具
- Shell 命令工具
- Web 搜索或网页提取工具
- 结构化输出
- 运行日志打印
- 最大迭代次数限制

## 推荐技术栈

- Python
- OpenAI 或 Anthropic API
- Pydantic / Instructor / PydanticAI（可选）
- Rich / Typer（可选，用于 CLI 展示）

## README 应该写什么

- 这个 Agent 解决什么问题
- 支持哪些工具
- Agent loop 如何工作
- 如何运行
- 示例输入输出
- 已知限制

## 进阶增强项

- checkpoint / resume
- tool timeout 与 retry
- 多模型 fallback
- session history

## 面试时如何讲

重点讲：
- 你如何设计 tool schema
- 如何避免无限循环
- 如何处理工具失败
- 为什么这样组织状态和日志
