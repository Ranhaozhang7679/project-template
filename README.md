# project-template

> 项目管理模板仓库 — 需求护航者 + 项目经理 Agent 共同维护

## 目录结构

```
project-template/
  README.md                              -- 本文件
  .gitignore

  docs/
    prd/                                 -- 📋 需求护航者产出
      project-onepager.md                  -- 项目一页纸
      requirements.md                      -- 完整需求文档（含 REQ 条目）
      boards/
        README.md                          -- 需求看板说明
        board-unified.html                 -- 需求看板（HTML，按状态/优先级排列）

    pm/                                   -- 📊 项目经理产出
      issue-template.md                    -- Issue 模板（关联 REQ、验收标准）
      iteration-plan-template.md           -- 迭代计划（里程碑、依赖图）
      requirement-matrix.md                -- 需求映射矩阵（REQ ↔ Issue 对照表）
      risk-register.md                     -- 风险登记（风险矩阵 + 缓解措施）
      milestone-review.md                  -- 里程碑评审（Go/No-Go）
      delivery-report.md                   -- 交付报告（版本交付确认）
      change-impact.md                     -- 变更影响评估（CR 触发）
      merge-decision-template.md           -- 合并决策记录
      pr-patrol-report-template.md         -- PR 巡检报告

    change-requests/                      -- 🔄 共用（变更管理）
      _template.md                         -- 变更请求模板（CR-{序号}.md）

    glossary.md                           -- 📖 术语表 + 编号规范（双方共用，唯一源）

  templates/                              -- 🎨 可视化渲染模板
    board-unified.html                     -- 需求看板 HTML（需求护航者用）
    requirement-item.md                    -- 需求条目模板
    dashboard.html                         -- 项目看板 HTML（实时+周报双模式）
    dashboard-data.md                      -- 项目看板数据源（YAML）
    milestone-review.html                  -- 里程碑评审看板 HTML
    risk-register.html                     -- 风险登记看板 HTML（含矩阵图）
```

## 编号规范

| 编号类型 | 格式 | 负责人 |
|----------|------|--------|
| 需求编号 | `REQ-{模块缩写}-{三位序号}` | 需求护航者 |
| 变更请求 | `CR-{三位序号}` | 需求护航者 |
| 任务编号 | `ISSUE-{三位序号}` | 项目经理 |
| 变更影响评估 | `CIA-{三位序号}`（与 CR 一一对应） | 项目经理 |
| 风险编号 | `R-{三位序号}` | 项目经理 |
| 里程碑 | `M{数字}` | 项目经理 |

> 完整规范见 `docs/glossary.md`

## 版本管理规则

| 操作 | Git 动作 | 触发者 |
|------|----------|--------|
| 需求锁定 | commit + tag（如 `prd-v1.0`） | 需求护航者 |
| 变更请求 | 创建分支 `cr/CR-001` + PR | 需求护航者 |
| CR 审核通过 | merge PR + 打新 tag（如 `prd-v1.1`） | 需求护航者 |
| 基线版本号 | Git tag: `prd-vX.Y`，文档内: `VX.Y` | 共用 |

## 协作流程

```
客户想法
  ↓
需求护航者：访谈 → 一页纸 → 拆需求(REQ) → 看板展示 → 锁定(tag) → 通知项目经理
  ↓
项目经理：解析需求 → 需求映射矩阵 → 拆 Issue → 排迭代计划
  ↓
开发执行 → PR → 项目经理巡检 + 合并决策
  ↓
项目经理：里程碑评审(Go/No-Go) → 交付报告
```

### 变更流程

```
客户变更需求
  ↓
需求护航者：创建 CR → 需求层面分析 → 通知项目经理
  ↓
项目经理：评估 CIA（执行层面影响）→ Owner 确认 → 调整计划
  ↓
需求护航者：合并 CR → 打新 tag
```

### 协作规则

- **通知机制**：需求护航者锁定 PRD 后通知项目经理，项目经理完成后回复确认
- **变更入口**：所有需求变更必须先经过需求护航者（创建 CR），不经 CR 的变更项目经理不接受
- **需求澄清**：验收标准最终解释权归需求护航者，Issue 标记 `need_clarification` 时通知需求护航者介入

## 使用方式

1. 基于本模板创建新仓库（项目名称作为仓库名）
2. 需求护航者在对话中完成需求捕获，推送 PRD 到 `docs/prd/`
3. 锁定后打 Git tag 并通知项目经理 Agent
4. 项目经理 Agent 通过 `gh` CLI 或本地仓库读取 PRD，产出排期和 Issue
5. 执行过程中项目经理定期产出巡检报告、周报、里程碑评审
6. 交付时产出交付报告
