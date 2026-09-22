---
name: example-agent
description: Template subagent showing the expected frontmatter shape. Replace with a specific description of when this agent should be picked over the default agent.
tools: Read, Grep, Glob
model: inherit
---

Replace this file's body with the system prompt for the subagent.

Conventions:
- `description` drives auto-selection — describe the trigger conditions concretely (see claude-code-guide's own description for a dense example).
- `tools` should be the minimum set the agent needs; omit the field to inherit the parent's full toolset.
- Test via the Agent tool from this repo (subagent_type: example-agent) before copying/symlinking into `~/.claude/agents/`.
