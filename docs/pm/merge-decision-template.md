# 合并决策记录

> 由项目推进者输出，格式固定，下�?Agent 和人工均可解析�?
```yaml
pr_number: "#XXX"
issue_ref: "ISSUE-XXX"
decision: "approved|changes_requested|rejected"
reviewer: "项目推进�?
reviewed_at: "YYYY-MM-DD"
```

---

## 合并决策�?*_批准 / 请求修改 / 拒绝_**

## 理由

> 引用 Issue 验收标准逐条说明�?
## 检查清�?
- [ ] CI 全绿
- [ ] 变更范围对应 Issue 验收点，无额外未授权改动
- [ ] 至少一名指定评审人（非作者）已查看且无反�?- [ ] 无回归风险标�?
## 详情

| 维度 | 结论 |
|------|------|
| 需求覆�?| _完整/部分，说明_ |
| 回归风险 | _�?无，说明_ |
| 变更范围 | _文件数、模块数_ |
| 评审人状�?| _列出评审人及意见_ |

---

## 给下�?Agent 的指�?
> �?decision=changes_requested，下�?Agent 据此修改代码�?
- 修改�?1：_
- 修改�?2：_
