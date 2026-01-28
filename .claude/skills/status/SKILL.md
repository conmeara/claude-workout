---
name: status
description: Show current training status and progress. Use when user asks about their progress, where they are in the program, or wants a summary.
allowed-tools:
  - Read
  - Glob
  - Grep
---

# Training Status Report

## Current Context
- Today: !`date +"%A, %B %d, %Y"`
- Workouts this week: !`ls -1 workouts/ 2>/dev/null | grep "$(date +%Y-%m)" | tail -7 || echo "None"`
- Recent PRs: !`tail -20 prs.md 2>/dev/null || echo "No PRs yet"`
- Active adjustments: !`cat adjustments.md 2>/dev/null | grep -v "^#" | grep -v "^$" | head -10 || echo "None"`

## Instructions

Read `program.md`, recent files in `workouts/` (last 7-14 days), `prs.md`, and `adjustments.md` to compile a status report.

## Output Format

```markdown
## Training Status

### Current Program
- **Plan:** [program name/style]
- **Week:** X of Y (if periodized)
- **Phase:** [e.g., accumulation, intensification, deload]

### This Week
- Workouts completed: X/Y
- Next scheduled: [workout name]

### Recent Activity (Last 7 Days)
| Date | Workout | Highlights |
|------|---------|------------|

### Active Adjustments
- [Any ongoing flags from adjustments.md]

### Recent PRs
- [Any PRs in the last 2 weeks]

### Trends
- [Observations: consistent training, missed sessions, fatigue accumulation, etc.]
```

If there's no plan, prompt the user to run `/plan`.
If there's no workout history, just show the plan overview.

Keep it concise - this is a quick status check.
