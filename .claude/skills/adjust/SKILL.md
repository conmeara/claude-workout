---
name: adjust
description: Flag an adjustment or life factor affecting training. Use when user reports fatigue, injury, schedule changes, or anything that should modify workouts.
allowed-tools:
  - Read
  - Write
  - Edit
---

# Flag Training Adjustment

## Current Context
- Current adjustments: !`cat adjustments.md 2>/dev/null || echo "No adjustments file"`
- Recent flags from workouts: !`grep -h "## Flags" workouts/*.md 2>/dev/null | head -10 || echo "No recent flags"`

## Instructions

The user wants to note something that should affect upcoming workouts:

- **Fatigue/Recovery:** "bad sleep", "stressful week", "feeling run down"
- **Minor injury/pain:** "shoulder is tweaky", "lower back tight"
- **Life factors:** "traveling next week", "only have dumbbells this week"
- **Training feel:** "feeling strong", "ready to push", "need a deload"
- **Schedule change:** "can only train 2x this week"
- **Resolved issue:** "shoulder feeling better now"

## Actions

1. Acknowledge the adjustment
2. Update `adjustments.md`:
   - Add new flag with date, description, impact, and expiry
   - If resolving an existing flag, remove that row
3. Explain how this will affect upcoming workouts:
   - What modifications will be made
   - How long the adjustment applies (ask if not clear)
   - When to revisit/clear the flag

## Format for adjustments.md

Add a new row to the table:

```markdown
| YYYY-MM-DD | [issue] | [modification] | [when to revisit] |
```

Example:
```markdown
| 2026-01-27 | Left shoulder tight | Reduce overhead volume, no HSPU negatives | Re-evaluate Friday |
| 2026-01-25 | Low sleep this week | Keep RPE under 7, reduce volume 20% | End of week |
```

The `/workout` skill reads this file and adapts accordingly.
