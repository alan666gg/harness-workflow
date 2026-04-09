# 文档顺序与索引建议

这份参考说明 harness 文档体系里常见的顺序和索引策略。

## 1. 入口文件应该短

入口文件的目标只有一个：

- 把人和线程带到正确位置

所以：

- `AGENTS.md` 短
- `README.md` 短
- `PLAN.md` 只管总盘

## 2. 推荐索引顺序

推荐让新线程按这个顺序启动：

1. `AGENTS.md`
2. `PLAN.md`
3. `docs/harness/README.md`
4. `roles/*.md`
5. `PROJECT_MAP.md`
6. `THREAD_PROTOCOL.md`
7. 当前 `Task`
8. 当前 `Handshake`
9. 当前 `Worklog`

## 3. 什么时候新增 Task

当任务满足任一条件时，建议新建 Task：

- 跨多个模块
- 需要多次推进
- 有清晰验收标准
- 需要交给其他线程

## 4. 什么时候只补 Worklog

当改动很窄时，可以不新建复杂设计文件，但至少要：

- 补一条 worklog
- 写清验证

## 5. Task / Handshake / Worklog 的关系

- Task：定义“要做什么”
- Handshake：定义“这条线程怎么做、能改哪里”
- Worklog：记录“实际做了什么”

三者不要混写。

## 6. 常见错误

### 错误 1：AGENTS.md 过长

后果：

- 每个线程都被迫读大量不必要内容

### 错误 2：Task 和 Handshake 合并成一个大文件

后果：

- 任务目标与线程合同混在一起，难复用

### 错误 3：Worklog 回写历史

后果：

- 执行轨迹失真

### 错误 4：计划和真实状态脱节

后果：

- 新线程判断优先级会出错

## 7. 推荐维护节奏

- 开始编码前：确认 task / handshake
- 每轮实现后：追加 worklog
- tranche 完成后：更新 plan
- 部署后：回写验证结果和 residual limitations
