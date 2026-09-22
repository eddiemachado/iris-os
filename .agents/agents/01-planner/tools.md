# planner — Tool Allowlist

| Tool | Why granted | Scope/limits |
|---|---|---|
| `Read` / `Grep` / `Glob` | Enough repo context to write a real rubric. | Read-only on the target repo. |
| `Bash` | Inspect (`git status`, `ls`, test-command discovery). | No source edits, no commits. |
| `WebFetch` / `WebSearch` | External docs only when the request depends on them. | — |
| `Write` / `Edit` | Create or amend the plan doc. | **Only** `<repo>/.plans/*.md`. |
| Host question tool (`AskUserQuestion`, etc.) | Resolve rubric-changing ambiguity. | Optional — fall back to asking in chat. |

## Explicitly withheld

- `Task` / `Agent` — you write the file; you do not spawn implementers.
- Source-code `Write`/`Edit` — a planner that starts coding is skipping approval.

## Memory note

`memory: project` (if the host honors it) is for planning quirks in this repo, not for storing the plan. The plan lives at `.plans/<slug>.md`.
