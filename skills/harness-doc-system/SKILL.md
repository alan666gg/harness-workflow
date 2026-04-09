---
name: harness-doc-system
description: 用于设计、补齐、审查或维护 harness 文档体系；适合需要规范 Plan、Task、Handshake、Worklog、目录结构和文档顺序的项目
---

# Harness 文档体系

## 概述

这个 skill 专门管 harness 的文档体系，不负责推进代码实现节奏。

它适合这些场景：

- 给一个仓库搭建 harness 目录
- 审查现有 harness 是否混乱
- 新增或更新 `Plan / Task / Handshake / Worklog`
- 把聊天里的设计结论归并进仓库
- 为后续 AI 线程建立稳定入口

如果任务重点是“继续开发并实现功能”，优先用：

- `harness-dev-workflow`

如果任务重点是“建立或维护文档/文件结构”，优先用：

- `harness-doc-system`

## 核心原则

1. **文档服务于执行**
   - 文档不是展示材料
   - 文档的目标是让线程更容易接手和继续做事

2. **入口少而稳定**
   - 顶层入口文件应尽量少
   - 让新线程能快速知道先读什么

3. **按职责分层**
   - Plan 管总方向
   - Task 管单条任务
   - Handshake 管线程合同
   - Worklog 管执行轨迹

4. **文件短、引用清楚**
   - 入口文件只做导航
   - 细节放到对应领域文档

5. **会话结论必须回写**
   - 重要决策不能只留在聊天里

## 什么时候用

- “给这个项目加一套 harness”
- “帮我整理 task / handshake / worklog”
- “这个文档结构太乱了，帮我重整”
- “把当前开发流程沉淀成可复用文件”
- “新增一个复杂 lane，需要补计划和任务文件”

## 标准文档顺序

推荐从这些入口开始：

1. `AGENTS.md`
2. `PLAN.md`
3. `docs/harness/README.md`
4. `docs/harness/PROJECT_MAP.md`
5. `docs/harness/THREAD_PROTOCOL.md`

然后再进入：

- 当前 task
- 当前 handshake
- 最新 worklog
- 相关领域代码和设计文档

## 文档体系的目标结构

推荐最小结构：

```text
docs/harness/
├── README.md
├── PROJECT_MAP.md
├── THREAD_PROTOCOL.md
├── roles/
├── plans/
├── tasks/
├── handshakes/
└── worklogs/
```

## 各文件职责

### AGENTS.md

只做入口导航，不要写成长手册。

应该包含：

- 仓库是什么
- 必读顺序
- 领域地图
- 核心文档入口

### PLAN.md

只维护项目总盘。

应该包含：

- source of truth 文件
- 当前主线
- 活跃任务
- 状态快照

### README.md（harness 目录）

告诉新线程：

- 这里有哪些文件夹
- 先读什么
- 各文件夹干什么

### PROJECT_MAP.md

解释：

- 仓库模块边界
- 核心目录职责
- 哪个问题应该去哪找

### THREAD_PROTOCOL.md

定义线程合同：

- 启动顺序
- handoff 规则
- worklog 规则
- commander / worker 角色关系

### Task

定义单条任务的：

- 目标
- scope
- ownership
- 验收标准

### Handshake

定义该任务对执行线程的明确合同：

- 允许改哪些文件
- 依赖什么
- 回来时要交什么

### Worklog

只做 append-only 记录：

- 读了什么
- 改了什么
- 验了什么
- 还剩什么

## 维护规则

1. 新知识优先写到对应领域文档，不堆在 AGENTS.md
2. 入口文件只做导航，不塞细节
3. 任务变化时，先改 task / handshake，再改代码
4. 工作日志必须追加，不回写历史
5. 任务完成后要更新 plan 状态

## 会话结论归并规则

聊天里产出的这些内容，要回写到仓库：

- 架构决策
- 任务边界
- blocker
- 验证结果
- residual limitations

回写位置建议：

- 总体方向 -> `PLAN`
- 单条任务 -> `Task`
- 线程约束 -> `Handshake`
- 执行过程 -> `Worklog`

## 审查清单

当你在审查 harness 文档体系时，逐项检查：

- [ ] 新线程能否在 5 分钟内找到启动顺序
- [ ] AGENTS.md 是否只是入口而不是大杂烩
- [ ] Task / Handshake / Worklog 是否职责清晰
- [ ] 是否存在重要决策只留在聊天里
- [ ] 当前 plan 是否能反映真实状态
- [ ] 领域地图是否足够指路

详细顺序与维护建议见：

- `references/doc-order-and-indexes.md`

