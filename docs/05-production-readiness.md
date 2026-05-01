# 生产化能力

如果目标是找工作，这一章非常关键。很多人会败在“只会 demo，不会工程化”。

## Observability：日志、Tracing、运行记录

你需要补齐：
- 结构化日志
- 每轮调用记录
- 工具调用轨迹
- 错误分类
- 成本 / token 使用记录
- 关键步骤可回放能力

## Evaluation：如何评估 Agent 是否真的好用

你要建立正确观念：
- 不能只靠“看起来挺聪明”评估 Agent
- 要设计任务集、成功标准、输出质量标准
- 要区分离线评估、人工评估和线上反馈

建议至少做一次：
- 为你的 Agent 设计 10~20 个真实测试任务
- 定义通过条件
- 比较不同 prompt / tool / planner 配置下的表现

## Reliability：稳定性设计

你需要理解：
- 超时
- 重试
- fallback
- 幂等
- 部分失败处理
- 外部依赖异常时的降级策略

这部分非常贴近真实岗位需求。

## Security：权限边界与风险控制

Agent 最大的风险之一就是“能力太强”。

你要开始关注：
- 文件系统权限边界
- shell / browser / network 工具的风险
- 敏感操作确认机制
- prompt injection / tool misuse
- secret management

## Cost 与 Latency 优化

在真实环境里，模型成本和延迟都要管理。

你需要理解：
- 什么时候该用更便宜模型
- 什么时候该减少循环次数
- 如何裁剪上下文
- 如何缓存结果
- 如何减少不必要的工具调用

## Deployment：把 Agent 真正交付出去

至少要知道这些交付形态：
- CLI 工具
- Web API / service
- 定时任务 / cron job
- 异步任务队列
- 消息平台 / chat gateway

建议至少完成一种真实部署。

## Config & Environment

这是工程成熟度的重要信号。

你需要学会：
- 配置文件管理
- 环境变量与密钥管理
- 多环境切换
- provider / model / tool 配置抽象
- 可迁移与可复现运行方式

## 阶段项目：可生产部署的 Agent 服务

建议第四个作品：
- 至少一种真实部署形态
- 有日志、配置、错误处理、评估样例
- 有 README、架构说明和运行说明
- 可以作为求职作品核心项目

## 这一章的完成标志

你应该能够：
- 不再只会 demo，而是具备基础生产能力
- 让项目支撑面试深入提问
- 用作品证明自己具备 Agent 工程岗位需要的成熟度

## 推荐资源

- Langfuse
  https://langfuse.com/
- Weights & Biases Weave
  https://wandb.ai/site/weave/
- OpenAI Evals
  https://github.com/openai/evals
- Arize Phoenix
  https://phoenix.arize.com/

建议：这一章要开始像工程师一样思考“如何证明系统稳定、可观测、可评估”。
