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

当前仓库提供 1 个核心 skill：

- `harness-dev-workflow`

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
```

### Claude Code / 兼容 agentskills.io 的环境

直接使用 `skills/harness-dev-workflow/SKILL.md` 即可。

## 仓库结构

```text
skills/
└── harness-dev-workflow/
    ├── SKILL.md
    └── references/
        ├── file-contracts.md
        └── validation-and-release.md
```

## 适合的团队场景

- AI 参与复杂代码开发
- 一个需求可能跨多个模块
- 需要把阶段性结论写回仓库
- 需要清晰的任务边界、验证证据、上线记录

## 状态

当前版本：`v1.0`

