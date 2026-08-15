# Agents

Native Claude Code subagents. Each agent is a single markdown file with frontmatter (`name`, `description`, `tools`) followed by its system prompt — see the [Claude Code subagent docs](https://docs.claude.com/en/docs/claude-code/sub-agents) for the format.

## Naming Convention

Files are named `role.md` — a short noun describing what the agent specializes in (e.g. `react-engineer.md`, `code-reviewer.md`). No category prefix or per-agent directory; that structure lived in the old `agents/[category]-role/` layout and didn't carry over to the native format.

## Adding a New Agent

1. Create `.agents/agents/role.md`
2. Add frontmatter: `name`, `description` (include trigger phrases so Claude Code knows when to invoke it), `tools` (comma-separated allowlist)
3. Write the system prompt as the body: expertise, approach, guidelines, response style
4. Keep the agent scoped to one specialty — don't build a generalist

## Current Agents

```
react-engineer   — Expert React 19.2 engineer for building modern frontend components
code-reviewer    — Reviews diffs for correctness, security, and simplification issues
```
