# 分支策略

> 团队统一的 Git 分支命名和保护规则。

## 分支命名规范

| 类型 | 格式 | 示例 | 说明 |
|------|------|------|------|
| 功能开发 | `feat/ISSUE-{序号}-{简述}` | `feat/ISSUE-003-login-page` | 对应一个 Issue |
| Bug 修复 | `fix/ISSUE-{序号}-{简述}` | `fix/ISSUE-007-null-pointer` | 对应一个 Issue |
| 变更请求 | `cr/CR-{序号}` | `cr/CR-001` | 对应一个 CR |
| 热修复 | `hotfix/{简述}` | `hotfix/critical-auth-bypass` | 紧急线上修复，不对应 Issue |

### 命名规则
- 全小写，单词间用 `-` 连接
- 简述控制在 3-5 个单词
- 必须关联 Issue 或 CR 编号（hotfix 除外）

## 分支保护

| 分支 | 规则 |
|------|------|
| `main` | 🔒 禁止直接 push，只能通过 PR 合并 |
| `feat/*` | 合并后删除 |
| `fix/*` | 合并后删除 |
| `cr/*` | 合并后删除 |
| `hotfix/*` | 合并后删除 |

## 分支生命周期

```
main ─────────────────────────────────────
  │                                         │
  ├── feat/ISSUE-001-desc                   │
  │     ↓ 编码 → 自测 → PR → 审查 → merge ──┘
  │
  ├── cr/CR-001
  │     ↓ 修改 PRD → PR → 审查 → merge → 新 tag
  │
  └── hotfix/xxx
        ↓ 修复 → PR → 审查 → merge
```

## 提交信息规范

```
<type>(<scope>): <subject>

<body>
```

### type 列表

| type | 说明 |
|------|------|
| `feat` | 新功能（对应 Issue） |
| `fix` | Bug 修复（对应 Issue） |
| `refactor` | 重构（不改变行为） |
| `test` | 新增或修改测试 |
| `docs` | 文档变更 |
| `chore` | 构建/工具/依赖变更 |

### 示例

```
feat(auth): implement login page

- Add login form component
- Add API integration for /api/auth/login
- Add unit tests for form validation

Refs: ISSUE-003
```
