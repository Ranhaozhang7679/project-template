# project-template

> 项目需求管理模板仓库 — 由「需求护航者」维护

## 目录结构

`
project-template/
├── README.md                        ← 本文件
├── docs/
│   ├── prd/
│   │   ├── project-onepager.md      ← 项目一页纸
│   │   ├── requirements.md          ← 完整需求文档
│   │   └── boards/
│   │       └── board-unified.html   ← 需求看板（HTML）
│   ├── change-requests/
│   │   └── _template.md             ← 变更请求模板
│   └── glossary.md                  ← 术语表
└── templates/                        ← 原始模板（供参考）
`

## 版本管理规则

| 操作 | Git 动作 |
|------|----------|
| 需求锁定 | commit + tag（如 `prd-v1.0`） |
| 变更请求 | 创建分支 `cr/CR-001` + PR |
| CR 审核通过 | merge PR + 打新 tag（如 `prd-v1.1`） |

## 使用方式

1. 基于本模板创建新仓库（项目名称作为仓库名）
2. 需求护航者在对话中完成需求捕获后，自动推送文档到此仓库
3. 下游项目经理 Agent 通过 `gh` CLI 读取最新基线

## 标签命名规范

- `prd-v{Major}.{Minor}` — 需求文档基线版本
- `cr-v{Major}.{Minor}` — 变更请求草稿（可选）
