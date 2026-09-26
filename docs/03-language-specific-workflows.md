# Language-Specific Codex Workflows

The same principles apply across languages, but the best patterns differ slightly by stack.

## Python

Best practices:

- Focus the prompt on the function, test, and exact failure
- Prefer patching one module before broad repo exploration
- Ask for type-safe implementations when the repo already uses typing
- Use the smallest relevant pytest or unit test command

Recommended prompt pattern:

> Fix the bug in `path/to/module.py`. Only inspect the function and the failing test context. Keep the patch minimal and type-safe. Do not refactor unrelated code. Return: root cause, patch summary, and the exact validation command.

## TypeScript / JavaScript

Best practices:

- Keep the prompt tied to one file or one API boundary
- Specify whether the issue is runtime, typing, or logic
- Prefer minimal edits over broad refactors
- Validate with the smallest relevant `npm test`, `vitest`, or `jest` target

Recommended prompt pattern:

> Fix the TypeScript bug in `src/...`. Only inspect the relevant module and its tests. Keep the patch minimal and idiomatic. Do not refactor unrelated code. Return the fix summary and the smallest exact validation command.

## Full-stack web / app repos

Best practices:

- Separate server-side bug from client-side bug
- Include only the relevant API contract or UI behavior
- Ask for minimal state changes and no unrelated cleanup
- Validate with the targeted route, component test, or local smoke test

Recommended prompt pattern:

> Diagnose and fix the frontend/backend issue in `<area>`. Use the minimal files required to confirm the contract and behavior. Keep the patch surgical. Return root cause, changed files, and the smallest validation command.

## Data / ML / notebooks

Best practices:

- Be specific about expected dataset behavior, metrics, or output shape
- Limit prompt payload to the exact notebook/cell or script
- Avoid asking for an entire pipeline rewrite unless the issue truly requires it

Recommended prompt pattern:

> Fix the data-processing bug in `<file>`. Keep the change limited to the affected logic and preserve existing output contracts. Return the root cause, patch summary, and the minimal validation step.

## General rule by stack

- Python: prioritize correctness + type clarity
- TypeScript: prefer minimal API contract changes
- Full-stack: separate the boundary clearly
- Data / ML: keep output semantics explicit

## Best practice for all languages

For every task, ask:

- What exactly is failing?
- What is the smallest file set needed?
- What is the smallest validation command?
- What output structure will keep the answer compact?

This keeps the workflow effective regardless of stack.
