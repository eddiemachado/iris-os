# Skills

Portable, standards-compliant Agent Skills (per [agentskills.io](https://agentskills.io)). Each skill lives in its own folder with a `SKILL.md` containing `name` and `description` frontmatter.

## Naming Convention

Skill folder and `name` frontmatter use `verb-noun` (no bracketed category prefix — that metadata now lives in the skill's `description`).

- **Verb** — the action the skill performs
- **Noun** — the target of that action

Example: `apply-motion` → applies motion to UI elements. What phase of work it belongs to (dev, QA, design, etc.) should be stated in the `description` so agents can match on intent rather than folder naming.

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
apply-motion   — Implement animations and transitions in UI code
```

---

## Adding a New Skill

1. Choose the closest existing verb; add a new one only if none fit
2. Name the folder: `verb-noun`
3. Create a `SKILL.md` inside with valid Agent Skills frontmatter (`name`, `description`, and any optional fields per agentskills.io)
4. Write a `description` that clearly states when the skill should be invoked, so agents can match on trigger context
5. Add an entry to the Current Skills list above
