# project-template

> 项目管理模板仓库 — 需求护航者 + 项目经理 + 程序员 Agent 共同维护

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
      issue-template.md                    -- Issue 模板（关联 REQ、验收标准、技术上下文）
      iteration-plan-template.md           -- 迭代计划（里程碑、依赖图）
      requirement-matrix.md                -- 需求映射矩阵（REQ ↔ Issue 对照表）
      risk-register.md                     -- 风险登记（风险矩阵 + 缓解措施）
      milestone-review.md                  -- 里程碑评审（Go/No-Go）
      delivery-report.md                   -- 交付报告（版本交付确认）
      change-impact.md                     -- 变更影响评估（CR 触发）
      merge-decision-template.md           -- 合并决策记录
      pr-patrol-report-template.md         -- PR 巡检报告
      pr-template.md                       -- PR 描述模板（程序员提交时使用）
      feedback-template.md                 -- 需求反馈单（程序员上报需求问题）

    change-requests/                      -- 🔄 共用（变更管理）
      _template.md                         -- 变更请求模板（CR-{序号}.md，含技术评估）

    branching-strategy.md                 -- 🌿 分支策略（命名规范 + 保护规则 + 提交信息规范）
    glossary.md                           -- 📖 术语表 + 编号规范（三方共用，唯一源）

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
项目经理：解析需求 → 需求映射矩阵 → 拆 Issue（含技术上下文） → 排迭代计划
  ↓
程序员：接收 Issue → 编码 + 自测 → 提交 PR（含 AC 覆盖 + 自测证据）
  ↓
项目经理：PR 巡检 + 合并决策
  ↓
项目经理：里程碑评审(Go/No-Go) → 交付报告
  ↓
需求护航者/客户：验收测试
```

### 变更流程

```
客户变更需求
  ↓
需求护航者：创建 CR → 需求层面分析
  ↓
程序员：技术评估（复杂度/工时/风险）
  ↓
项目经理：评估 CIA（综合业务价值+技术成本）→ Owner 确认 → 调整计划
  ↓
需求护航者：合并 CR → 打新 tag
```

### 协作规则

- **通知机制**：需求护航者锁定 PRD 后通知项目经理，项目经理完成后回复确认
- **变更入口**：所有需求变更必须先经过需求护航者（创建 CR），不经 CR 的变更项目经理不接受
- **需求澄清**：验收标准最终解释权归需求护航者，Issue 标记 `need_clarification` 时项目经理通知需求护航者介入
- **需求反馈**：程序员发现需求问题时提交反馈单（FB），项目经理路由到澄清或 CR 流程
- **测试职责**：单元/集成/自测归程序员，PR 巡检/回归评估归项目经理，验收归需求护航者/客户
- **分支策略**：详见 `docs/branching-strategy.md`

## 使用方式

1. 基于本模板创建新仓库（项目名称作为仓库名）
2. 需求护航者在对话中完成需求捕获，推送 PRD 到 `docs/prd/`
3. 锁定后打 Git tag 并通知项目经理 Agent
4. 项目经理 Agent 通过 `gh` CLI 或本地仓库读取 PRD，产出排期和 Issue（含技术上下文）
5. 程序员 Agent 接收 Issue，按分支策略创建分支，编码自测后提交 PR
6. 项目经理巡检 PR + 合并决策，定期产出巡检报告、里程碑评审
7. 验收通过后产出交付报告
