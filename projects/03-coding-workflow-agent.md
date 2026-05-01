# Coding / Workflow Agent

## 项目目标

构建一个面向代码任务或多步骤工作流的 Agent，能够进行计划、执行、审查和总结。

## 这个项目要证明什么

它主要证明你具备：
- planning / task decomposition 能力
- 文件与工具编排能力
- review loop 能力
- workflow 设计与状态流转能力

## 最小功能范围

建议至少支持：
- 读取和修改文件
- 生成执行计划
- 执行多步骤任务
- 审查结果并二次修正
- 输出最终总结

## 推荐技术栈

- Python
- 文件工具 + shell 工具
- 可选接入 Git
- 可选接入测试命令

## README 应该写什么

- 这个 Agent 面向什么任务
- planning 与 execution 如何协作
- 如何处理失败和回滚
- review loop 如何设计
- 有哪些安全边界

## 进阶增强项

- checkpoint / rollback
- 多子任务并行
- reviewer / critic 子代理
- Git commit 建议

## 面试时如何讲

重点讲：
- 为什么需要 planning
- 什么时候需要 review loop
- 如何控制对代码和文件系统的风险
- 如何判断任务已经完成
