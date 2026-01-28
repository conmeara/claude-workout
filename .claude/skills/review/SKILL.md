---
name: review
description: Weekly progress review - summarize training, PRs, issues, and recommendations. Use at end of week or when user wants a deeper look at progress.
allowed-tools:
  - Read
  - Glob
  - Grep
---

# Weekly Progress Review

## Current Context
- This week's workouts: !`ls -1t workouts/ 2>/dev/null | head -7 || echo "None"`
- All PRs: !`cat prs.md 2>/dev/null || echo "No PRs yet"`
- Current adjustments: !`cat adjustments.md 2>/dev/null || echo "None"`
- Program overview: !`head -40 program.md 2>/dev/null || echo "No program"`

## Instructions

Compile a comprehensive weekly review by reading:
- All workout files from the past 7 days in `workouts/`
- `prs.md` for PR tracking
- `adjustments.md` for ongoing issues
- `program.md` for program adherence

## Output Format

```markdown
## Weekly Review - [Date Range]

### Summary
- **Workouts completed:** X/Y scheduled
- **Adherence:** [percentage or qualitative assessment]
- **Overall trend:** [progressing / maintaining / regressing / recovering]

### Highlights
- [Best performances, breakthroughs, PRs]

### Concerns
- [Recurring issues, flags that persisted, missed sessions]

### Volume & Intensity
| Day | Workout | Estimated Volume | Notes |
|-----|---------|------------------|-------|

### PR Tracker
| Exercise | Previous Best | New Best | Improvement |
|----------|---------------|----------|-------------|

### Patterns Noticed
- [Sleep/energy correlations, exercise-specific trends, recovery observations]

### Recommendations for Next Week
1. [Specific, actionable recommendation]
2. [Another recommendation]
3. [Consider deload? Push harder? Address an issue?]

### Questions to Consider
- [Prompt user to reflect on something]
```

Be analytical but concise. Focus on actionable insights, not just data regurgitation.

If this is the 4th or 5th week, proactively assess if a deload is needed.
