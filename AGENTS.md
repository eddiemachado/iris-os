# AGENTS.md

**Never** edit or add anything to this file. This is maintained by a human.

- Be terse and concise. 
- Don't use overly-technical jargon.
- When offering options, always explain why this decision is needed as well as the pros/cons of each choice. Be terse in your explanations.
- If you leave comments in the code, keep them to two lines maximum.
- Secrets stay in the vault, never in code.
- Do not make any changes outside of the planned scope. If a bug or issue is found, flag it with the user but do not fix it.

## Architecture
To better understand this repo's architecture, read `ARCHITECTURE.md`.

## Design
When working with any UI or styling, read `DESIGN.md`.

## Git 
When working with Git, always refer to the rules in `.agents/rules/git.md`.

## Linear
When working with Linear or task management, always refer to `.agents/rules/linear.md`.

## Plans
- Keep plans terse and concise. No backstory, no redundant sections, no separate files unless asked.
- Don't add rejected decisions made during planning, only those relevant to the current plan goal.
- Before finalizing a plan, list everything in scope. That includes content changes, cross-references and script path fixes, not just the literal file operation.
- Do not execute anything while in plan mode.

## Figma
- Use [Figma CLI](https://github.com/silships/figma-cli) by default, if not installed use the Figma MCP server.