# Tools

Tools this agent is authorized to use, and why each is included.

| Tool | Purpose |
|---|---|
| `codebase` | Read existing components and patterns before implementing |
| `search` | Find similar implementations already in the codebase |
| `edit/editFiles` | Write and modify component files |
| `new` | Create new files |
| `runCommands` | Run dev server, builds, linters |
| `runTests` | Verify components with the test suite |
| `findTestFiles` | Locate existing test files before writing new ones |
| `problems` | Check TypeScript and linting errors after edits |
| `fetch` | Pull external docs (React docs, MDN, package readmes) |
| `terminalLastCommand` | Review the last command output for build/test errors |
| `usages` | Find where a component or hook is used before refactoring |
| `changes` | Review current diff before finalizing implementation |

## Tools intentionally excluded

- `githubRepo` — this agent operates on the local codebase, not external repos
- `vscodeAPI` / `extensions` — environment-specific; not required for implementation tasks
- `microsoft.docs.mcp` — use `fetch` for docs instead; keeps tool surface minimal
