# project-template

> 项目需求管理模板仓库 — 由「需求护航者」维护

## 目录结构

```
project-template/
  README.md
  .gitignore
  docs/
    prd/
      project-onepager.md            -- 项目一页纸
      requirements.md                -- 完整需求文档
      boards/
        README.md                    -- 看板目录说明
    change-requests/
      _template.md                   -- 变更请求模板
    glossary.md                      -- 术语表
    shared-workspace/                -- 多Agent共享工作区模板
      handoff/
        handoff.md                   -- 交接状态
        context.json                 -- 项目上下文
      version/
        version-map.json             -- 版本映射表
        repo-url                     -- GitHub仓库地址
      tasks/
        task-list.md                 -- 任务清单模板
        sprint-01.md                 -- Sprint计划模板
      code/
        progress.md                  -- 开发进度模板
      changelog.md                   -- 变更日志
  templates/
    requirement-item.md              -- 需求条目模板
    board-unified.html               -- 看板HTML模板
```

## 本地共享工作区

每个项目在本地使用 `F:\SharedWorkspace\projects\<项目名>\` 作为多Agent公共工作区：

- 所有Agent的输入输出都在此工作区内
- 按角色分目录，遵循读写权限规则
- 通过 `handoff/` 目录实现Agent间交接
- 通过 `version/` 和 `changelog.md` 跟踪版本变更
- 锁定时同步推送到GitHub仓库

## 版本管理规则

| 操作 | Git 动作 |
|------|----------|
| 需求锁定 | commit + tag（如 `prd-v1.0`） |
| 变更请求 | 创建分支 `cr/CR-001` + PR |
| CR 审核通过 | merge PR + 打新 tag（如 `prd-v1.1`） |

## 使用方式

1. 基于本模板创建新仓库（项目名称作为仓库名）
2. 需求护航者在对话中完成需求捕获后，写入共享工作区并推送到GitHub
3. 项目经理通过共享工作区读取PRD，拆分任务
4. 程序员通过共享工作区读取任务，更新开发进度

## 标签命名规范

- `prd-v{Major}.{Minor}` — 需求文档基线版本
- `cr-v{Major}.{Minor}` — 变更请求草稿（可选）