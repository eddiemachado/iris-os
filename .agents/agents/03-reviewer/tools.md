# reviewer — Tool Allowlist

| Tool | Why granted | Scope/limits |
|---|---|---|
| `Read` | Read the plan doc, diff, review file, repo conventions (`CLAUDE.md`, lint config, etc.). | — |
| `Grep` / `Glob` | Locate relevant files/config to evaluate against. | — |
| `Bash` | Run tests/linters as verification (not mutation), read `git diff`/`status`/`log`. | Read/verify only — never `commit`, `push`, `reset`, or any command that mutates the repo under review. This is a convention, not a sandboxed guarantee; treat it as load-bearing anyway. |
| `SendMessage` | Send PASS/FAIL verdicts to `orchestrator`. | — |

## Explicitly withheld

- **`Task`/`Agent`** — genuinely absent. A reviewer that can spawn workers stops being an independent check.
- **`Write`/`Edit` for anything outside `agent-memory`** — not explicitly requested in this list; see Memory note below for where Write/Edit actually come from and their real scope.

## Offload Convention

Outputs over roughly 20K tokens (large diffs, full test logs) should be written to a scratch path with a preview kept in context, not carried in full. Not yet mechanically enforced; apply it yourself.

## Memory note

`memory: project` in the registration frontmatter auto-grants Read/Write/Edit for `.claude/agent-memory/reviewer/` in whichever repo you're reviewing. This is the *only* place Write/Edit exist for you — never use them against the repository under review, under any circumstance. Whether this is technically enforced by Claude Code or purely a matter of following this instruction is unconfirmed; act as if it's the latter.
