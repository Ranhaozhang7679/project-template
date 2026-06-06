# Issue 模板

> 由项目推进者生成，下游开�?Agent 据此执行。结构化字段不可省略�?
```yaml
issue_id: "ISSUE-XXX"
title: ""
req_ref: "REQ-{模块}-{序号}"          # 关联 PRD 需求编�?baseline_version: "VX.Y"    # PRD 基线版本
milestone: "M?"             # 所属里程碑
priority: "P0|P1|P2|P3"
complexity: "S|M|L|XL"
assignee: ""                # 飞书 open_id �?Agent ID
status: "todo|in_progress|blocked|done"
created_at: "YYYY-MM-DD"
due_date: "YYYY-MM-DD"
```

---

## 目标

> 一句话说明�?Issue 要达成什么。下�?Agent 据此判断自己是否应该接手�?
---

## 输入

> 完成�?Issue 需要的前置条件（数据、接口、设计稿、其�?Issue 产出物）�?
- 输入 1：_
- 输入 2：_

---

## 输出

> �?Issue 完成后必须产出的交付物（文件、接口、配置、文档等）�?
- 输出 1：_
- 输出 2：_

---

## 验收标准

> 逐条引用 PRD 验收标准，下�?Agent 必须逐项自检�?
- [ ] AC-1：_（引�?PRD 原文）_
- [ ] AC-2：_
- [ ] AC-3：_

## 约束

> 技术边界、不允许的做法、必须遵循的规范�?
- 约束 1：_
- 约束 2：_

---

## 依赖

```yaml
depends_on: []    # ISSUE-XXX 前置任务
blocks: []        # ISSUE-XXX 被本 Issue 阻塞的任�?related: []       # ISSUE-XXX 关联任务
```

---

## 审查指引

> 告知下游 Agent：提�?PR 时需确保以下内容�?PR 描述中体现�?
- PR 描述必须引用�?Issue 编号
- PR 描述必须逐条说明验收标准的实现情�?- 如有未完成项，必须标注原�?
---

## 变更记录

| 日期 | 操作 | 说明 |
|------|------|------|
| YYYY-MM-DD | 创建 | 项目推进者基�?REQ-XXX 生成 |
