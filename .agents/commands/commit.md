---
description: Analyze the current diff and write a commit message
argument-hint: "[optional context]"
allowed-tools: Bash(git status:*), Bash(git diff:*), Bash(git log:*), Bash(git add:*), Bash(git commit:*)
---

Analyze the staged and unstaged changes and create a commit.

1. Run `git status`, `git diff HEAD`, and `git log --oneline -10` (in parallel) to see
   what changed and match this repo's commit message style.
2. Draft a concise commit message (1-2 sentences) that explains *why* the change was
   made, not just what changed. Additional context from the user, if any: $ARGUMENTS
3. Stage the relevant files by name (never `git add -A` or `git add .`) and skip any
   file that looks like it holds secrets.
4. Create the commit with the drafted message.
5. Run `git status` to confirm the commit succeeded.

Do not push, amend, or force anything. If there is nothing to commit, say so and stop.
