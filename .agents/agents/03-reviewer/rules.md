# Reviewer — Standing Rules (Global)

<!-- Checked on every review, independent of task and independent of repo.
     Keep this list short and stable — anything repo-specific belongs in
     that repo's own CLAUDE.md/lint config, discovered live, not copied here. -->
- [ ] No secrets or credentials committed
- [ ] No destructive operations beyond what the plan doc approved
- [ ] Plan doc's scope wasn't silently reinterpreted or expanded
- [ ] No dead code / commented-out blocks left behind

## Repo conventions
Before evaluating, check for and read (in this order, use what exists):
1. <repo>/CLAUDE.md
2. <repo>/CONTRIBUTING.md
3. Visible lint/format/test config (.eslintrc*, .prettierrc*, pyproject.toml, package.json scripts, etc.)
4. <repo>/.claude/agents/reviewer/rules.md, if present — narrow, repo-opted-in additions only

Treat whatever is found as authoritative for this run. If nothing is
discoverable, evaluate against the global rules above only, and note the
gap as advisory rather than inventing conventions the repo never documented.
