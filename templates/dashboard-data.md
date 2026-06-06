# 项目仪表盘数�?
> 结构化数据源，HTML 仪表盘从此文件读取。项目推进者每次更新时同步更新此文件�?
```yaml
dashboard:
  updated_at: "YYYY-MM-DD HH:MM"
  baseline_version: "VX.Y"
  health: "green|yellow|red"

  summary:
    total: 0
    done: 0
    in_progress: 0
    todo: 0
    blocked: 0
    overdue: 0

  milestones:
    - id: "M1"
      name: ""
      deadline: "YYYY-MM-DD"
      total: 0
      done: 0
      status: "not_started|in_progress|completed|blocked"
      risk: "none|low|medium|high"
    - id: "M2"
      name: ""
      deadline: "YYYY-MM-DD"
      total: 0
      done: 0
      status: "not_started"
      risk: "none"

  blockers:
    - item: "ISSUE-XXX"
      type: "blocker|overdue"
      reason: ""
      impact: ""
      assignee: ""
      eta: "YYYY-MM-DD"

  regression:
    milestone: "M?"
    round: 1
    result: "pass|fail|running"
    pass_rate: "0%"
    note: ""

  pr_status:
    open: 0
    reviewable: 0
    ci_failed: 0
    stale: 0

  weekly_focus: []
```
