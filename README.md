# AI Agent 学习路线图

面向具备 Python、API 调用、Linux/终端基础，并希望进入 AI Agent 工程岗位的开发者。

## 这份路线图适合谁

这份 roadmap 面向已经具备以下基础的学习者：
- 会使用 Python 进行日常开发
- 理解 HTTP / API 调用、JSON、认证等基本概念
- 能在 Linux / WSL / macOS 终端中完成常见开发操作
- 希望进入以 AI Agent、LLM 应用、自动化智能体、Agent System 为方向的工程岗位

这份路线图不面向完全零基础编程新手，也不以纯理论研究为核心目标。重点是：构建真正可运行、可评估、可部署、可展示的 Agent 工程能力。

## 学完后的目标

完成这条路线后，你应该能够：
- 独立构建一个支持工具调用的单 Agent 系统
- 为 Agent 接入 memory、RAG、planning、review loop 等能力
- 设计基础的多 Agent / workflow 架构
- 为 Agent 系统补齐日志、评估、配置、重试、权限边界等生产能力
- 看懂并上手 Hermes、Claude Code、OpenClaw、MCP 等相关生态
- 产出可用于求职的 GitHub 项目与作品集

## 学习主线

这份路线图围绕三条主线展开：
1. 能力主线：从模型调用到 Agent 系统设计
2. 项目主线：每一阶段都产出可运行项目
3. 求职主线：每一阶段都沉淀为可展示作品与面试表达

---

## Phase 0：先建立正确的 Agent 心智模型

### 1. 什么是 AI Agent

先不要急着学框架。先理解：Agent 不是“一个更长的 prompt”，而是一个能够在环境中感知、决策、调用工具、维护状态并持续执行任务的系统。

你至少要能回答这些问题：
- Assistant、Workflow、Agent 有什么区别？
- 什么任务适合 Agent，什么任务不适合？
- 为什么很多所谓 Agent 其实只是工作流封装？
- 一个最小可用 Agent 通常由哪些部分组成？

### 2. 建立最小系统视角

你要形成一个基本框架：
- Model：负责推理与生成
- Tools：负责和外部世界交互
- Memory：负责跨步骤或跨会话保留信息
- State：负责当前任务上下文
- Planner / Policy：负责决定下一步做什么
- Environment：Agent 实际操作的目标世界

建议在这一阶段重点理解“Agent loop”，而不是死记概念。

### 3. 这一阶段的完成标志

- 能用自己的话解释什么是 Agent
- 能区分一次性问答、工作流编排和真正的 Agent 系统
- 能画出一个最小 Agent 架构图

---

## Phase 1：构建你的第一个可用 Agent

这一阶段的目标是：从“会调模型”进化到“能做一个真正可运行的单 Agent”。

### 1. 模型调用与结构化输出

你需要熟练掌握：
- Chat Completions / Responses 类接口的基本使用
- system / user / assistant message 结构
- temperature、max tokens、上下文长度等常见参数
- JSON / schema / structured output 的基本约束方式

你不需要一开始就深挖所有 provider 差异，但必须能稳定完成：
- 调用模型
- 解析结构化结果
- 对失败结果做基本兜底

### 2. Tool Calling / Function Calling

这是进入 Agent 工程的第一道门槛。

你需要学会：
- 什么是 tool schema
- 模型如何选择工具
- 如何执行工具并把结果回填给模型
- 如何处理工具错误、超时、空结果和异常返回

建议最先实现的工具类型：
- 文件读写
- Shell 命令执行
- Web 搜索 / 页面提取
- 简单计算或数据处理

### 3. Agent Loop 与状态管理

一个最小可用 Agent 至少要有：
- 任务输入
- 循环调用模型
- 识别是否需要工具调用
- 执行工具
- 把结果继续送回模型
- 在满足条件后结束

你还需要理解：
- 什么时候该停止循环
- 如何限制最大迭代次数
- 如何保存中间状态
- 如何防止 Agent 无限循环

### 4. Prompt 设计与任务约束

在 Agent 场景下，prompt 的重点不是“写华丽提示词”，而是：
- 角色与目标边界
- 工具使用规范
- 输出格式约束
- 错误处理策略
- 成功标准定义

你要学会把任务描述成“可执行说明”，而不是模糊愿望。

### 5. 错误处理、重试与日志

很多 demo 能跑，但不稳定。工程上必须补上：
- API 重试
- 工具失败重试
- 超时控制
- 运行日志
- 中间步骤记录
- 基础调试信息输出

### 6. 阶段项目：CLI Tool-Using Agent

建议你完成第一个作品：
- 一个命令行 Agent
- 支持至少 3 类工具
- 能显示每一步执行过程
- 能处理常见失败情况
- 有清晰 README

这是你进入 Agent 岗位前必须具备的最小项目。

这一阶段的完成标志：
- 你能从零写出单 Agent loop
- 你理解 tool calling 的完整闭环
- 你有一个可运行的 CLI Agent 项目

---

## Phase 2：让 Agent 变得更强

这一阶段的目标是：让 Agent 不只是“能跑”，而是“开始有实际价值”。

### 1. Memory：短期记忆与长期记忆

你需要区分：
- 短期记忆：当前会话上下文
- 长期记忆：跨会话持久信息
- 用户画像 / 偏好 / 环境信息
- 外部存储与内部上下文的边界

你不需要一开始就做复杂 memory 系统，但要理解：
- 什么信息值得记住
- 什么信息不应该记住
- Memory 如何影响 Agent 稳定性与个性化

### 2. RAG：让 Agent 接入外部知识

RAG 是很多 Agent 项目的基础能力。

你需要掌握：
- 文档切分、嵌入、召回的基本流程
- 如何把检索结果安全地注入上下文
- 如何避免“检索了但没用上”
- 如何要求引用来源或 grounded output

建议至少完成一次：
- 本地文档知识库接入
- 查询 -> 检索 -> 总结 -> 引用来源 的完整闭环

### 3. Planning：任务拆解与执行计划

当任务变长、多步、依赖复杂时，Agent 需要 planning。

你需要理解：
- 什么时候该显式规划，什么时候不该过度规划
- task decomposition 的基本形式
- planner-executor 结构
- 计划更新与中途修正

### 4. Reflection / Review Loop

这是很多高质量 Agent 的关键差异点。

你需要尝试：
- 自检输出是否满足格式和目标
- 二次审查结果是否合理
- 对工具执行结果进行 review
- 失败后重新规划或重试

注意：reflection 不是无限回环，而是可控的质量提升手段。

### 5. Human-in-the-loop

真正能用于生产的 Agent，常常不能完全自动化。

你要理解：
- 哪些步骤必须让人确认
- 哪些操作可以自动执行
- 如何在交互中保留用户控制权
- 如何设计 approve / reject / revise 的流程

### 6. Checkpoint / Resume

长任务里，恢复能力很重要。

你应开始理解：
- 如何保存中间状态
- 如何恢复执行进度
- 如何记录运行上下文
- 如何避免因中断导致整个流程重来

### 7. 阶段项目：Research Agent 或 Coding Assistant

建议第二个作品二选一：
- Research Agent：支持检索、整理、引用、结构化输出
- Coding Assistant：支持文件操作、计划、修改、审查、总结

这一阶段的完成标志：
- 你能把 memory / RAG / planning 接入一个真实项目
- 你理解 agent 的“持续执行”而不是单轮回答
- 你拥有第二个更像真实产品的作品

---

## Phase 3：从单 Agent 到 Agent System

这一阶段的目标是：理解更复杂的系统组织方式，而不是只会一个单循环 Agent。

### 1. 为什么需要多 Agent

不是所有问题都需要多 Agent。你要先搞清楚：
- 多 Agent 真正解决了什么问题
- 它适合并行拆分、角色分工、复杂工作流还是组织隔离
- 什么时候多 Agent 只是增加复杂度

### 2. 常见多 Agent 模式

建议重点掌握这几类：
- Router：根据任务路由到不同能力单元
- Planner / Executor：一个负责规划，一个负责执行
- Manager / Worker：一个负责拆任务，多个执行子任务
- Reviewer / Critic：一个生成，一个审查

### 3. Shared State 与消息传递

多 Agent 系统的难点不只是“多开几个模型调用”，而是：
- 状态怎么共享
- 上下文怎么隔离
- 任务边界如何定义
- 结果如何汇总
- 失败如何回滚或重试

### 4. 并发与结果聚合

你要开始思考工程问题：
- 哪些任务可以并发
- 哪些步骤必须串行
- 如何聚合多个子结果
- 如何避免上下文爆炸
- 如何做 timeout / cancellation

### 5. 结合代表性系统理解设计

在这一阶段，你可以开始系统性观察：
- Hermes：工具系统、技能、记忆、delegation、cron、gateway
- Claude Code：编码任务循环、工具调用、代码工作流
- OpenClaw：代理式代码与任务执行范式

重点不是“会用产品按钮”，而是理解这些系统背后的工程抽象。

### 6. 阶段项目：Multi-Agent Workflow

建议第三个作品：
- 拥有 router 或 manager-worker 结构
- 支持多个子任务协同
- 支持状态记录与结果聚合
- 有失败处理与基本可观测能力

这一阶段的完成标志：
- 你知道什么时候该用多 Agent，什么时候不该用
- 你能实现一个基本的 orchestrated workflow
- 你能解释 Hermes / Claude Code / OpenClaw 一类系统的关键设计思路

---

## Phase 4：生产化能力是岗位真正看重的部分

如果你想找工作，这一阶段非常关键。很多人会败在“只会 demo，不会工程化”。

### 1. Observability：日志、Tracing、运行记录

你需要补齐：
- 结构化日志
- 每轮调用记录
- 工具调用轨迹
- 错误分类
- 成本 / token 使用记录
- 关键步骤可回放能力

### 2. Evaluation：如何评估 Agent 是否真的好用

你要建立正确观念：
- 不能只靠“看起来挺聪明”评估 Agent
- 要设计任务集、成功标准、输出质量标准
- 要区分离线评估、人工评估和线上反馈

建议至少做一次：
- 为你的 Agent 设计 10~20 个真实测试任务
- 定义通过条件
- 比较不同 prompt / tool / planner 配置下的表现

### 3. Reliability：稳定性设计

你需要理解：
- 超时
- 重试
- fallback
- 幂等
- 部分失败处理
- 外部依赖异常时的降级策略

这部分非常贴近真实岗位需求。

### 4. Security：权限边界与风险控制

Agent 最大的风险之一就是“能力太强”。

你要开始关注：
- 文件系统权限边界
- shell / browser / network 工具的风险
- 敏感操作确认机制
- prompt injection / tool misuse
- secret management

### 5. Cost 与 Latency 优化

在真实环境里，模型成本和延迟都要管理。

你需要理解：
- 什么时候该用更便宜模型
- 什么时候该减少循环次数
- 如何裁剪上下文
- 如何缓存结果
- 如何减少不必要的工具调用

### 6. Deployment：把 Agent 真正交付出去

至少要知道这些交付形态：
- CLI 工具
- Web API / service
- 定时任务 / cron job
- 异步任务队列
- 消息平台 / chat gateway

建议至少完成一种真实部署。

### 7. Config & Environment

这是工程成熟度的重要信号。

你需要学会：
- 配置文件管理
- 环境变量与密钥管理
- 多环境切换
- provider / model / tool 配置抽象
- 可迁移与可复现运行方式

### 8. 阶段项目：可生产部署的 Agent 服务

建议第四个作品：
- 至少一种真实部署形态
- 有日志、配置、错误处理、评估样例
- 有 README、架构说明和运行说明
- 可以作为求职作品核心项目

这一阶段的完成标志：
- 你会的不再只是 demo，而是基础生产能力
- 你的项目能支撑面试深入提问
- 你的作品能证明你具备 Agent 工程岗位需要的成熟度

---

## 重点生态与工具地图

这一部分不是为了追新，而是为了建立工具坐标系。

### 1. 模型接口层

优先理解：
- OpenAI 风格 tool calling
- Anthropic 风格工具使用
- 结构化输出与 schema 约束

这是所有上层系统的基础。

### 2. Agent 编排层

可以按“理解思路”的方式学习：
- LangGraph：更偏 workflow / state graph
- AutoGen：多 agent 对话与协作
- CrewAI：角色化 agent 工作流

目标不是全都精通，而是知道它们各自想解决什么问题。

### 3. 协议与集成层：MCP

MCP 很值得学，因为它直接关系到 Agent 如何接入外部工具生态。

你需要理解：
- MCP 解决的核心问题是什么
- 工具暴露和调用的边界在哪里
- 为什么 MCP 会成为很多 Agent 系统的关键集成方式

### 4. 实战型 Agent 系统

建议重点研究：
- Hermes
- Claude Code
- OpenClaw

研究方式不是“当普通用户使用”，而是观察：
- 它们如何组织 prompt、toolsets、memory、session、workflow
- 它们如何处理长任务、中断恢复、多工具执行
- 它们如何向工程系统演进

### 5. 对框架的基本态度

你要尽量避免一个误区：
“把学会某个框架，误认为学会了 Agent 工程。”

更健康的顺序是：
- 先理解核心能力
- 再学框架如何封装这些能力
- 最后根据场景选型

---

## 求职导向：如何证明你真的会做 Agent

如果目标是找到岗位，你需要的不只是学习，还要能证明能力。

### 1. 简历要体现什么

尽量围绕这些能力写：
- tool-using agent 开发
- memory / RAG / planning / orchestration
- evaluation / observability / deployment
- 成本、稳定性、安全等工程考量

不要只写“使用过某框架”。

### 2. GitHub 项目如何组织

建议你的作品集至少包含：
- 1 个 CLI Agent
- 1 个 RAG / Research Agent
- 1 个 Coding / Workflow Agent
- 1 个更完整的 production-style Agent 项目

每个仓库都要具备：
- 清楚的 README
- 架构说明
- 运行方式
- 示例输入输出
- 已知限制
- 后续改进方向

### 3. README 应该写什么

至少包括：
- 这个 Agent 解决什么问题
- 为什么用这种架构
- 支持哪些工具与能力
- 如何运行
- 如何评估
- 限制与 tradeoff

### 4. 面试时怎么讲

你要能讲清楚：
- 为什么这样设计 Agent loop
- 为什么选这种工具接入方式
- 什么时候加入 memory / RAG / planner
- 多 Agent 带来了什么收益和成本
- 你是如何做稳定性、评估和部署的

真正拉开差距的，通常就是这些 tradeoff 表达能力。

### 5. 建议完成的作品集清单

建议最终至少完成以下 4 个项目：
- CLI Tool-Using Agent
- Research / RAG Agent
- Coding / Workflow Agent
- Production-Style Agent System

如果时间有限，至少保证前 2 个做扎实，后 2 个做出有工程味道的版本。

---

## 一个建议的 12 周学习节奏

### 第 1~2 周
- 补齐 Agent 基础心智模型
- 熟练模型调用与结构化输出
- 手写最小 tool calling 闭环

### 第 3~5 周
- 做出第一个 CLI Agent
- 补日志、重试、状态管理
- 完成第一个可展示项目

### 第 6~8 周
- 学 memory、RAG、planning、review loop
- 完成 Research Agent 或 Coding Assistant

### 第 9~10 周
- 学多 Agent / workflow 编排
- 研究 Hermes、Claude Code、OpenClaw 等系统的设计
- 做一个多 Agent 小项目

### 第 11~12 周
- 补 observability、eval、deployment、安全边界
- 打磨 README、项目结构、演示材料
- 把项目整理成求职作品集

---

## 推荐的学习策略

### 1. 永远围绕“项目 + 文档 + 复盘”学习

不要只看教程。最有效的方式是：
- 学一个能力
- 做一个小模块
- 写下设计理由与踩坑记录

### 2. 优先看官方文档和真实代码

优先级建议：
1. 官方文档
2. 官方示例
3. 高质量开源仓库
4. 论文和博客
5. 二手教程视频

### 3. 学框架时不要失去底层理解

无论是 LangGraph、MCP、Hermes 还是 Claude Code 相关生态，都尽量搞清楚：
- 它们底层抽象了什么
- 帮你省掉了什么
- 又限制了什么

### 4. 持续积累“可证明能力”

每学一个阶段都问自己：
- 我能不能做成一个独立项目？
- 我能不能写出清楚 README？
- 我能不能在面试中讲清 tradeoff？

如果答案是否定的，就说明还没真正学会。

---

## 最后：判断自己是否具备基础 Agent 岗位竞争力

如果你已经能够做到下面这些事，通常就具备了不错的初级 Agent 工程岗位竞争力：
- 能独立实现单 Agent + tool calling 系统
- 能把 memory、RAG、planning 接入实际任务
- 能设计一个基础多 Agent workflow
- 能为 Agent 系统补日志、评估、部署与错误处理
- 能看懂 Hermes / Claude Code / OpenClaw 这类系统的核心设计思路
- 能用 GitHub 项目把这些能力清晰展示出来

真正有竞争力的人，不是“看过很多 Agent 概念”，而是“做过一批可运行、可复盘、可展示的 Agent 项目”。

如果你按这条路线踏实推进，最终收获的不只是知识清单，而是一套可以拿去找工作的工程能力体系。
