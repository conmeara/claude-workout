---
name: log
description: Log a completed workout. Use when user wants to record what they did in their training session.
allowed-tools:
  - Read
  - Write
  - Glob
---

# Log Completed Workout

## Current Context
- Today's date: !`date +"%Y-%m-%d"`
- Existing PRs: !`cat prs.md 2>/dev/null | head -30 || echo "No PRs yet"`

## Instructions

Ask the user to describe their workout:
- What exercises did they do?
- What sets/reps/progressions did they hit?
- How did it feel? (RPE, energy level)
- Any pain, discomfort, or issues?
- Any notes or observations?

The user can provide this in any format - casual description is fine. Parse it into the structured format.

## Actions

1. Parse the user's input into the structured workout log format
2. Create a new file in `workouts/` named `YYYY-MM-DD.md` (today's date)
   - If a file for today already exists, append or ask if they want to replace
3. Check if any lifts are PRs by comparing to `prs.md`:
   - If a PR is detected, congratulate briefly and update `prs.md`
   - For bodyweight progressions, a PR is hitting a new progression level or new rep/time record
4. If there are flags (pain, fatigue, issues), add them to `adjustments.md`

## Log Format

Create `workouts/YYYY-MM-DD.md`:

```markdown
# YYYY-MM-DD - [Workout Name/Day]

## Exercises
| Exercise | Sets x Reps | Weight/Progression | Notes |
|----------|-------------|-------------------|-------|

## Session Notes
- [User's qualitative feedback]

## Flags
- [Any concerns to track, or "None"]
```

Confirm to the user that the workout has been logged and mention any PRs or flags noted.
