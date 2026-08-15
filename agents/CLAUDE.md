# Agents — Naming & Structure Guide

## Naming Convention

All agents follow the pattern: `[category]-role`

- **Category** (in brackets) — the phase of work or domain this agent operates in
- **Role** — what this agent specializes in (a noun, not a verb)

Example: `[dev]-react-engineer` → invoked during development, acts as a React engineering specialist.

---

## Category Vocabulary

Uses the same categories as skills:

| Category | When to use it |
|---|---|
| `[ds]` | Design system — agents that curate, evolve, or govern tokens and components |
| `[design]` | Figma, visual design decisions, design-team workflows |
| `[dev]` | Implementation — building, refactoring, or reviewing code |
| `[qa]` | Quality — testing, auditing, reviewing for correctness |
| `[plan]` | Planning, syncing tools (Linear, Jira), specs, strategy |
| `[git]` | Version control — PRs, commits, changelogs, releases |
| `[content]` | Copy, labels, messaging, translation |

**Rule:** Same as skills — pick the phase of work where someone would invoke this agent, not all the domains it touches internally.

---

## Directory Structure

Each agent lives in its own directory:

```
agents/[category]-role/
├── AGENT.md          — persona, expertise, approach, guidelines, response style
├── tools.md          — which tools this agent is allowed to use and why
├── memory.md         — gaps and insights logged during real use
├── memory-archive/   — cleared memory preserved for historical reference
│   └── YYYY-MM.md
└── evals.md          — success criteria and anti-patterns for evaluating output
```

### File responsibilities

- **AGENT.md** — the static definition: who the agent is, what it knows, how it behaves. Updated by the improvement loop, not by hand during normal use.
- **tools.md** — documents the tool list and why each tool is included. The frontmatter in AGENT.md is the enforcement layer; this file explains the rationale.
- **memory.md** — dynamic file. The agent appends brief entries when it encounters gaps, uncertainty, or corrections during real tasks. Reviewed weekly and cleared after improvements are applied.
- **memory-archive/** — dated snapshots of cleared memory. Preserves the history of what was learned and when, so future editors can understand why AGENT.md contains certain rules.
- **evals.md** — defines what "good" looks like. Updated as part of the improvement loop when new failure modes are discovered.

## Memory Improvement Loop

Agents are improved on a weekly cadence using the `[plan]-improve-agents` skill:

```
Agent works
  → logs gaps and insights to memory.md (instructed by AGENT.md)

[plan]-improve-agents runs weekly
  → skips agents with empty memory.md
  → reads memory.md + AGENT.md + profiles/[agent].md
  → proposes targeted improvements to AGENT.md and evals.md
  → human reviews and applies changes

Post-approval
  → memory.md contents moved to memory-archive/YYYY-MM.md
  → memory.md reset to empty
```

Over time, gaps should become less frequent as improvements are applied — memory files stay slim.

---

## Current Agents

```
[dev]-react-engineer   — Expert React 19.2 engineer for building modern frontend components
[design]-engineer      — (scaffold only — not yet defined)
```

---

## Adding a New Agent

1. Pick the category that matches when a developer would reach for this agent
2. Name the directory: `[category]-role`
3. Create `AGENT.md` with frontmatter: `name`, `version`, `description`, `triggers`, `tools`
4. Create `memory.md` (with the standard empty template) and `evals.md`
5. Create `memory-archive/` directory
6. Create a profile in `skills/[plan]-improve-agents/profiles/[category]-role.md` with improvement focus notes
7. Add an entry to the Current Agents list above
