# Iris OS

Ways of working with AI that includes skills, agents, and context templates.

## Project overview

Iris OS is a platform-agnostic foundation for AI coding agents: skills, subagent
definitions, and context/rules files that work the same way whether you're
driving them from Claude Code, Codex, Cursor, Gemini CLI, or another tool.

The goal is one source of truth per capability, not N near-duplicate copies
that drift out of sync as each tool's config format evolves.

## Canonical extension points

- **`.agents/skills/`** — real, portable `SKILL.md` files following the open
  [Agent Skills](https://agentskills.io) spec. Read natively by Claude, Codex,
  Cursor, Gemini CLI, Copilot, VS Code, OpenCode, and Kimi CLI — no per-tool
  adapter needed.
- **`.agents/agents/`** — subagent definitions. Currently Claude-native format,
  since no open cross-tool subagent standard exists yet.

Add or edit skills and agents in `.agents/`, not inside any tool-specific
folder — tool folders should only ever point into `.agents/`, never hold
their own copy of the content.

## `.claude/` symlink structure

`.claude/skills` and `.claude/agents` are **symlinks** into `../.agents/skills`
and `../.agents/agents` respectively. This lets Claude Code read the same
canonical content through its native `.claude/` folder without a second copy
existing anywhere. Everything else Claude-specific (`settings.json`, hooks,
commands, output styles, rules) lives directly in `.claude/`, since those
don't have open cross-tool equivalents yet.

**Windows caveat:** git only checks out real symlinks (instead of plain text
files containing the link path) when `core.symlinks` is enabled. Run
`git config core.symlinks true` before cloning/checking out on Windows, or the
`.claude/skills` and `.claude/agents` symlinks will show up broken.
