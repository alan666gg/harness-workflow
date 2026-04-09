# 文件合同

这份参考说明 harness 工作流里的几类核心文件该承载什么信息。

## 1. Plan

用途：

- 记录项目总目标
- 维护阶段状态
- 指明当前优先级

至少包含：

- 当前 source-of-truth 文件
- 战略分层
- 当前进行中的任务
- 已完成的重要 tranche
- 下一步焦点

## 2. Task

用途：

- 定义单条任务的目标与验收范围

至少包含：

- task id
- 背景
- 目标
- 非目标
- ownership
- 输入文档
- 需要触达的代码边界
- 验收标准

## 3. Handshake

用途：

- 让执行线程知道这条任务能改什么、不能改什么

至少包含：

- task id
- owner 线程 / 角色
- scope
- dependencies
- files to touch
- expected output
- blockers
- handoff notes

## 4. Worklog

用途：

- 记录 append-only 的真实执行过程

每条记录建议包含：

- timestamp
- read
- changed
- validated
- blockers / next

## 5. 什么时候只用 Task，不单独补设计文档

当任务满足下面条件时，可以不额外写长文档：

- 影响范围小
- 不改架构边界
- 不引入新术语
- 不涉及迁移/部署策略变化

这时把：

- 目标
- 约束
- 验证口径

写清楚到 task / handshake 就够了。

## 6. 什么时候必须补架构说明

这些情况建议显式补文档：

- 新增服务或新链路
- 改 truth boundary
- 改权限或风控语义
- 改部署路径
- 改资金、账本、结算、链上合约边界

