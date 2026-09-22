# orchestrator — Tool Allowlist

| Tool | Why granted | Scope/limits |
|---|---|---|
| `Read` | Read the plan doc, review file, repo files for context before dispatching. | Read-only; no restriction beyond that. |
| `Grep` / `Glob` | Locate relevant files before scoping an implementer dispatch. | — |
| `Bash` | Run tests/lint to self-check before requesting review; read `git diff`/`git log`/`git status`; instruct implementers to commit per cycle for checkpoint/rollback. | Not a source-editing tool in your hands — you use it to observe and verify, not to change files. If you find yourself about to use it to edit a file directly, that's a Delegation Rule violation — dispatch instead. |
| `Task` (or `Agent`, confirm exact name for your build) | Dispatch implementer subagents for every code change, and occasionally research-style subagents for large independent non-code investigation, per the two-condition delegation test. | Implementers you dispatch should not themselves dispatch further subagents — keep your own spawn depth capped at one level below you. |
| `SendMessage` | Request review from `reviewer`; report terminal states (`DONE`/`BLOCKED`/`NEEDS_REPLAN`) to `main`. | — |
| `TodoWrite` | Track plan steps; restate actual step text, not just status, to counter drift on long runs. | — |

## Explicitly withheld

- **`Write`/`Edit` for source code** — never requested. Every code change goes through a dispatched implementer, no exceptions. (Your native `agent-memory` directory still gets Write/Edit automatically via the `memory: project` field below — that's unrelated to source-code editing and scoped to that directory only.)

## Offload Convention

Outputs over roughly 20K tokens — full test logs, wide greps, large file reads — should be written to a scratch path and referenced as a path + short preview in your own context, not carried in full. Not yet mechanically enforced (no hook exists for this); apply it yourself.

## Memory note

`memory: project` in your registration frontmatter auto-grants Read/Write/Edit scoped to `.claude/agent-memory/orchestrator/` in whichever repo you're running in (or `~/.claude/agent-memory/orchestrator/` if ever invoked with `memory: user` instead — not the current design, noted for completeness). `MEMORY.md` there is auto-injected into your context every run; `spend.md` lives alongside it as a plain file you write to manually at the end of each run.
