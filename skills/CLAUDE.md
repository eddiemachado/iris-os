# Skills — Naming & Structure Guide

## Naming Convention

All skills follow the pattern: `[category]-verb-noun`

- **Category** (in brackets) — the phase of work or domain where this skill is invoked
- **Verb** — the action the skill performs
- **Noun** — the target of that action

Example: `[dev]-apply-motion` → invoked during development, applies motion to UI elements.

---

## Category Vocabulary

| Category | When to use it |
|---|---|
| `[ds]` | Design system — selecting or navigating tokens, components, or system elements |
| `[design]` | Figma, visual design decisions, design-team workflows |
| `[dev]` | Implementation — writing, applying, or migrating code |
| `[qa]` | Quality checks — audits, a11y, coverage, correctness |
| `[plan]` | Planning, syncing tools (Linear, Jira), specs, strategy |
| `[git]` | Version control — PRs, commits, changelogs, branch workflows |
| `[content]` | Copy, labels, messaging, translation |

**Rule:** The category answers "what phase of work are you in when you'd invoke this?" — not "what does the skill touch internally?" Use this to resolve ambiguity for cross-cutting skills.

---

## Verb Vocabulary

Keep the verb list small and consistent. Prefer these:

| Verb | Meaning |
|---|---|
| `select` | Choose one thing from a set |
| `apply` | Transform or add something to existing work |
| `generate` | Create something new from scratch |
| `audit` | Analyze existing state for issues or coverage |
| `migrate` | Convert from one pattern or system to another |
| `format` | Enforce a consistent structure or shape |
| `plan` | Produce a structured plan, spec, or strategy |
| `sync` | Align with an external tool or source of truth |

Avoid inventing new verbs if an existing one fits. New verbs should be added here when established.

---

## Current Skills

```
[ds]-select-token          — Choose the right design token for a use case
[ds]-select-component      — Choose the right component from the design system
[dev]-apply-motion         — Implement animations and transitions in UI code
[qa]-audit-tokens          — Audit the codebase for token usage consistency
[qa]-audit-components      — Audit the codebase for component usage consistency
```

---

## Adding a New Skill

1. Pick the category that matches when a developer would reach for this skill
2. Choose the closest existing verb; add a new one only if none fit
3. Name the folder: `[category]-verb-noun`
4. Create a `SKILL.md` inside with frontmatter: `name`, `version`, `description`, `triggers`
5. Add an entry to the Current Skills list above

**If a skill crosses multiple categories**, pick the one that matches the trigger context — the moment a developer would invoke it, not the layers it touches internally.
