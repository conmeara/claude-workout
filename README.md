# Claude Workout Coach

A persistent AI training coach built on Claude Code. Tracks workouts, manages periodization, detects PRs, and adapts to your life.

## Getting Started

1. Clone this repo
2. Open it with Claude Code: `claude`
3. Say hi

The coach will introduce itself and get to know you — your background, goals, equipment, and preferences. Then you'll build your first program together.

## File Structure

```
claude-workout/
│
├── CLAUDE.md                 # Coach identity, protocols, and memories
├── user-profile.md           # Your info (filled in as coach learns about you)
├── program.md                # Your training plan (built together)
├── prs.md                    # Personal records
├── adjustments.md            # Active flags (injuries, fatigue, schedule)
│
├── workouts/                 # One file per session
│   └── YYYY-MM-DD.md
│
└── .claude/
    ├── settings.json
    ├── rules/formats.md
    ├── skills/               # Slash commands
    │   ├── workout/          # /workout
    │   ├── log/              # /log
    │   ├── status/           # /status
    │   ├── plan/             # /plan
    │   ├── adjust/           # /adjust
    │   └── review/           # /review
    └── agents/
        ├── analyzer.md       # Deep progress analysis
        └── program-builder.md # Periodized program design
```

## How It Works

The coach reads context files before each response — your profile, program, recent workouts, PRs, and active adjustments. No re-explaining yourself every session.

### Skills

| Command | Purpose |
|---------|---------|
| `/workout` | Generate today's session |
| `/log` | Record completed workout |
| `/status` | Quick progress summary |
| `/plan` | Create or update program |
| `/adjust` | Flag injuries, fatigue, schedule changes |
| `/review` | Weekly progress analysis |

### Agents

| Agent | Purpose |
|-------|---------|
| `analyzer` | Deep trend analysis across workout history |
| `program-builder` | Design periodized programs with mesocycles |

## Daily Workflow

```
/workout          # Get today's session
[train]
/log              # Record what you did
```

## Weekly

```
/review           # Analyze the week, recommendations
```

## Logging Workouts

Just describe naturally:

> "Did upper today. Pull-ups 3x8, felt strong. Dips 3x6, harder than expected. Left shoulder a bit tight."

The coach structures it, checks for PRs, and notes flags.

## Customization

- **Profile**: Edit `user-profile.md` or tell the coach about changes
- **Coaching style**: Edit the `Vibe` section in `CLAUDE.md`
- **Program**: Run `/plan` or edit `program.md` directly
