# 迭代计划表

> 由项目推进者生成，下游 Agent 据此安排执行顺序。

```yaml
plan_id: "PLAN-XXX"
baseline_version: "V?.?"
created_at: "YYYY-MM-DD"
status: "draft|locked|executing|completed"
```

---

## 里程碑

```yaml
milestones:
  - id: "M1"
    name: ""
    start: "YYYY-MM-DD"
    end: "YYYY-MM-DD"
    issues: ["ISSUE-XXX", "ISSUE-XXX"]
    deliverables: []
    status: "not_started|in_progress|completed"
  - id: "M2"
    name: ""
    start: "YYYY-MM-DD"
    end: "YYYY-MM-DD"
    issues: ["ISSUE-XXX"]
    deliverables: []
    status: "not_started|in_progress|completed"
```

---

## Issue 排列（按执行顺序）

| 序号 | Issue | 标题 | 里程碑 | 负责人 | 优先级 | 复杂度 | 状态 | 开始 | 截止 |
|------|-------|------|--------|--------|--------|--------|------|------|------|
| 1 | ISSUE-XXX | _标题_ | M1 | _待分配_ | P1 | M | 📋 | YYYY-MM-DD | YYYY-MM-DD |

---

## 依赖关系

```
ISSUE-001 ──→ ISSUE-003 ──→ ISSUE-005
ISSUE-002 ──→ ISSUE-004
```

> 下游 Agent 注意：箭头指向的 Issue 必须等箭头源 Issue 完成后才能开始。

---

## 风险摘要

> 详细风险信息见 `docs/pm/risk-register.md`，此处仅列出与本迭代直接相关的风险 ID。

| 风险 ID | 概要 | 影响里程碑 | 等级 |
|---------|------|-----------|------|
| R-XXX | _概要_ | M? | 高/中/低 |

---

## 变更记录

| 日期 | 版本 | 变更内容 |
|------|------|---------|
| YYYY-MM-DD | V1.0 | 初始计划锁定 |
