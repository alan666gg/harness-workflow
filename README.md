# harness-workflow

一个中文 AI 开发工作流 skill，融合两类实践：

- `doc-driven-dev` 的“文档先行、测试对齐、再写代码”
- harness 的“Plan / Task / Handshake / Worklog 文件化编排”

目标不是把开发流程写得更重，而是让复杂开发任务变得：

- 可拆分
- 可追踪
- 可复现
- 可交接
- 可验证

## Skill

当前仓库提供 3 个核心 skill：

- `harness-dev-workflow`
- `harness-doc-system`
- `harness-commander`

它适合：

- 开始一个新功能
- 恢复一个中断的大任务
- 推进跨后端 / 前端 / 合约 / 测试环境的长链路开发
- 需要把 AI 开发过程沉淀到仓库，而不是只留在聊天里

## 核心理念

1. 文档先于代码，但不过度文档化
2. 仓库文件是 source of truth，不依赖聊天记忆
3. 复杂任务先拆成 task，再进入实现
4. 每条任务都要有验证闭环
5. 小改动走窄流程，大改动走全流程
6. 单线程可执行，多线程可扩展

## 推荐目录约定

```text
docs/harness/
├── plans/
├── tasks/
├── handshakes/
└── worklogs/
```

## 安装

### Codex

```bash
git clone https://github.com/alan666gg/harness-workflow.git ~/.codex/harness-workflow
mkdir -p ~/.agents/skills
ln -s ~/.codex/harness-workflow/skills/harness-dev-workflow ~/.agents/skills/harness-dev-workflow
ln -s ~/.codex/harness-workflow/skills/harness-doc-system ~/.agents/skills/harness-doc-system
ln -s ~/.codex/harness-workflow/skills/harness-commander ~/.agents/skills/harness-commander
```

### Claude Code / 兼容 agentskills.io 的环境

直接使用 `skills/` 目录下的三个 skill：

- `skills/harness-dev-workflow/SKILL.md`
- `skills/harness-doc-system/SKILL.md`
- `skills/harness-commander/SKILL.md`

## 仓库结构

```text
skills/
├── harness-dev-workflow/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── file-contracts.md
│       └── validation-and-release.md
├── harness-doc-system/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       └── doc-order-and-indexes.md
└── harness-commander/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
templates/
├── task-template.md
├── handshake-template.md
└── worklog-template.md
```

## 适合的团队场景

- AI 参与复杂代码开发
- 一个需求可能跨多个模块
- 需要把阶段性结论写回仓库
- 需要清晰的任务边界、验证证据、上线记录

## 三个 skill 的分工

### `harness-dev-workflow`

负责：

- 复杂任务推进
- tranche 拆分
- task / handshake / worklog 闭环
- 验证与发布节奏

### `harness-doc-system`

负责：

- harness 目录设计
- Plan / Task / Handshake / Worklog 的写法规范
- 文档顺序
- 索引与回写纪律

### `harness-commander`

负责：

- 拆任务
- 分 ownership
- 维护总计划
- 把多个 tranche 收成统一验收结果

## 模板

仓库现在也包含可直接复用的模板：

- `templates/task-template.md`
- `templates/handshake-template.md`
- `templates/worklog-template.md`

## 状态

当前版本：`v1.0`
