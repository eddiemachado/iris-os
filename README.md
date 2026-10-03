# iris-os

Ways of working with AI that includes skills, agents, and context templates

## Retro

`/retro` reviews how recent agent runs went and files improvement tickets in Linear. It never changes agents or rules itself. A person reads the tickets and decides what to fix.

### When to run it

Run `/retro` whenever you want a check-up, and at least every 30 days. It reads Claude Code's session history, which Claude Code deletes after 30 days by default.

Each machine keeps its own history, so run it on every machine you use. A reminder (`.agents/hooks/retro-reminder.sh`) appears when you start a session if `/retro` hasn't run on that machine in 7 days and there are sessions to review.

- `/retro`: everything since the last retro.
- `/retro 7`: the last 7 days.
- `/retro <session-id>`: one session.

### How it works

1. **Summarize.** A script reads this repo's session history and produces a short summary: tokens used per agent, errors, blocked actions, oversized outputs, files read over and over, and review verdicts. Claude only reads this summary, not the full history, which keeps it cheap.
2. **Add context.** It reads the plan review files (`.agents/.plans/*.review.md`) and the agents' memory notes.
3. **Find problems.** It looks for wasted tokens, repeated failures, unclear plan criteria, reviewer false alarms, gaps between instruction files, and memory notes that should become real rules.
4. **File tickets.** It creates up to 5 tickets per run in the Linear project **Iris** with the label **retro**. If a matching ticket is already open, it adds a comment instead of a duplicate.

### Memory vs. retro

Agents learn in two ways:

- **Memory (fast, unreviewed).** The orchestrator and reviewer write short notes to their memory when something goes wrong. The note is loaded on their next run, so the same mistake is less likely to happen again right away. Nobody reviews these notes.
- **Retro (slower, reviewed).** `/retro` spots lessons that matter long term and files a ticket. A person updates the real rule. The ticket also says which memory note to delete afterwards, so each lesson lives in one place.

### Where the data lives

| What | Where | Shared? |
|---|---|---|
| Session history | `~/.claude/projects/<repo-path>/` | No, this machine only |
| Last retro marker | `.retro-last` in the folder above | No |
| Agent memory | `.agents/agent-memory/<agent>/` | Yes, in git |
| Plans and reviews | `.agents/.plans/` | No, gitignored; `/retro` deletes finished ones |

### Setup

Run `/mcp` once and log in to Linear. Without it, `/retro` still lists what it found but can't create tickets.
