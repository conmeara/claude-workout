# File Formats

Standard formats for all workout-related files.

## Workout Log Format

Each workout gets its own file in `workouts/YYYY-MM-DD.md`:

```markdown
# YYYY-MM-DD - [Workout Name/Day]

## Exercises
| Exercise | Sets x Reps | Weight/Progression | Notes |
|----------|-------------|-------------------|-------|
| Pull-ups | 3x8 | Bodyweight | RPE 7, felt strong |

## Session Notes
- How it felt, energy level, any observations

## Flags
- Any concerns to monitor (e.g., "left shoulder tight", "low energy")
- Or "None" if no issues
```

## PR Format

In `prs.md`:

```markdown
## Exercise Name
| Date | Weight/Progression | Reps | Estimated 1RM | Notes |
|------|-------------------|------|---------------|-------|
```

For bodyweight progressions, track the progression level instead of weight:
- "Advanced Tuck FL" instead of "225 lbs"
- "Ring Dips" instead of weight for progression PRs

## Adjustments Format

In `adjustments.md`:

```markdown
# Active Adjustments

| Date | Flag | Impact | Expires |
|------|------|--------|---------|
| 2026-01-27 | Left shoulder tight | Reduce overhead volume | Re-evaluate Friday |
```

When flags resolve, remove them from the table.

## Program Format

In `program.md`:

```markdown
# Training Plan

## Overview
- **Goal:** [primary goal]
- **Days per week:** X
- **Program style:** [style]
- **Started:** YYYY-MM-DD

## Schedule
[Day-by-day breakdown]

## Progression Scheme
[How to advance]

## Deload Protocol
[When and how]

## Workout Templates
[Detailed templates for each workout day]
```
