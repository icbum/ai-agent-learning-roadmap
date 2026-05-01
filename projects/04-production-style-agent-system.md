# Production-Style Agent System

## 项目目标

构建一个更接近真实交付形态的 Agent 系统，而不只是本地 demo。

## 这个项目要证明什么

它主要证明你具备：
- observability 能力
- evaluation 能力
- deployment 能力
- 配置管理、稳定性和安全边界设计能力

## 最小功能范围

建议至少支持：
- 一种真实交付方式（CLI / API / 定时任务 / chat gateway）
- 配置文件或环境变量管理
- 基础日志和运行记录
- 错误处理与超时控制
- 至少一组评估样例

## 推荐技术栈

- Python
- FastAPI / Typer / queue 系统（按场景选）
- Langfuse / Phoenix / Weave（可选）
- Docker（可选）

## README 应该写什么

- 系统架构
- 部署方式
- 配置项说明
- 运行与调试方式
- 评估方法
- 已知限制与后续规划

## 进阶增强项

- 多模型路由
- 异步任务执行
- scheduled jobs
- metrics dashboard
- 权限控制与审计日志

## 面试时如何讲

重点讲：
- 为什么它比 demo 更接近生产系统
- 你如何做 observability 和 eval
- 如何处理成本、超时、失败和配置管理
- 如果要真正上线，你下一步会补什么
