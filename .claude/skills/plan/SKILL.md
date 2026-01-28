---
name: plan
description: Create or update the training plan. Use when user wants a new program or to modify their current one.
allowed-tools:
  - Read
  - Write
  - Edit
  - WebSearch
  - Task
---

# Create or Update Training Plan

## Current Context
- Existing plan: !`head -20 program.md 2>/dev/null || echo "No plan exists yet"`
- User profile: !`cat user-profile.md 2>/dev/null | head -30`

## Instructions

### For New Users (no profile yet)

If `user-profile.md` is mostly empty, have a conversation first:

> Let's build something that actually fits your life. Tell me a bit about yourself — what's your training background, what are you working with equipment-wise, and what are you hoping to achieve?

Learn about them naturally, then update `user-profile.md` before building the program.

### For Existing Users

If you already know them, confirm what they want:
- New program from scratch?
- Modify current program?
- Change goals or schedule?

### Building the Program

For complex programs (periodized, skill-focused, or intermediate+), use the **program-builder** agent — it understands mesocycles, progression models, and evidence-based programming.

For simple programs (beginner linear progression), you can build directly.

### The Program Should Include

1. **Overview** — Goals, duration, days/week, session length
2. **Weekly structure** — What happens each day
3. **Progression scheme** — Exactly how to advance
4. **Mesocycle plan** — Phases and their purpose
5. **Workout templates** — Detailed exercises for each day
6. **Deload protocol** — When and how to back off
7. **Benchmarks** — How to measure progress

### After Building

1. Write the complete program to `program.md`
2. Update `user-profile.md` with any new info learned
3. Explain the program briefly — why it fits them
4. Tell them to run `/workout` when they're ready to start

### Program Design Principles

- **Simple > Complex** — Earn complexity through consistency
- **Sustainable > Optimal** — They need to actually do it
- **Adaptable** — Life happens, programs should flex
- Match periodization to experience:
  - Beginner: Linear progression
  - Intermediate: Undulating or simple block periodization
  - Advanced: Block periodization, specialized phases
