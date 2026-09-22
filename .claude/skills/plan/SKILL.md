---
name: plan
description: >
  Write a portable plan document at .plans/<slug>.md with ordered steps and a
  required Acceptance Criteria rubric before any implementation. Use when the
  user asks to plan or design an approach, when work is non-trivial and no
  approved plan doc exists, when orchestrator reports NEEDS_PLAN or
  NEEDS_REPLAN, or when normalizing a Cursor, Claude, or Codex Plan Mode draft
  into the iris-os schema. Do not implement code; stop for user approval, then
  the main session may invoke orchestrator with the plan path.
---

# /plan — Write the plan doc

Host Plan Mode (Cursor, Claude, Codex) is optional. The artifact that matters is the file.

1. Read `.agents/agents/01-planner/agent.md` and `.agents/agents/01-planner/references/plan-doc.md`.
2. Follow that role: explore just enough, ask when the rubric would otherwise be guessed, write `<repo>/.plans/<slug>.md`.
3. Leave `status: draft` until the user clearly approves.
4. Stop. Report the path. Do not implement. Do not invoke `orchestrator` from this skill — the main session does that after approval, with `plan_doc` set to the file you wrote.

If a draft already exists in a host-specific location, rewrite or copy it into `.plans/<slug>.md` so orchestrator and reviewer see one schema.
