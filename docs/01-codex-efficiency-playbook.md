# Codex Efficiency Playbook

## Objective

Make Codex more effective at the same time you reduce token waste, lower latency, and improve patch quality. The winning pattern is not “more context” but “better-scoped context.”

## The big idea

Every prompt is a tradeoff between:

- quality of output
- token spend
- time to completion
- risk of over-exploration

The best prompting behavior is:

- precise
- minimal
- constrained
- validated
- reusable

## 1. Prompt design principles

### Keep it narrow
Only include the necessary files, functions, and error details. Avoid dumping large codebases into the prompt.

Good:
- one file
- one bug
- exact error
- expected behavior

Bad:
- whole repo dump
- broad design speculation
- repeated unrelated context

### Ask for the smallest acceptable implementation
When possible, say:

- fix this bug
- keep patch minimal
- do not refactor unrelated code
- validate with the smallest relevant test

### Make output structured
Instead of letting Codex produce long, freeform explanation, request a structure such as:

- root cause
- files changed
- patch summary
- validation command
- risk notes

This helps keep output compact and easier to verify.

### Bias toward surgical edits
Prioritize:

- local fixes
- minimal diffs
- existing patterns
- checked assumptions

Avoid:

- broad rewrites
- speculative abstractions
- style churn
- unrelated cleanup

## 2. Context management rules

Use these heuristics:

- Start with only the target file
- Add adjacent file only if needed
- Include exact failing output or stack trace
- Exclude noisy logs unless required
- Avoid quoting full JSON dumps or large transcripts

## 3. Output controls that save tokens

Good output instructions:

- “Code only.”
- “Return summary + patch + validation command.”
- “Keep explanation to 3 bullets.”
- “Do not refactor unrelated files.”

Use output constraints to reduce decorative prose and accidental verbosity.

## 4. Validation strategy

The highest ROI validation is usually:

- one targeted test
- one lint check
- one compile check
- one smoke run

Not everything. Not broad suites. Not full regression passes unless required.

## 5. Prompt template pattern

Use this structure for most engineering tasks:

- Objective
- Relevant files
- Constraints
- Desired output
- Validation

Example:

> Act as a senior engineer. Fix the bug in `src/api/user.ts`. Only inspect the specific file and the exact API contract needed to diagnose the issue. Keep the patch minimal. Do not refactor unrelated code. Validate with the smallest relevant test command. Return: 1) root cause 2) code patch summary 3) validation command.

## 6. Cost-aware decision rules

Use a medium-effort default for regular tasks. Use higher effort only when:

- the problem is truly hard
- code is highly coupled
- the fix requires reasoning across several files
- you need a wider search before patching

If the task is routine or repetitive, prefer narrower prompts and smaller context windows.

## 7. What high-efficiency Codex usage looks like

Efficient behavior includes:

- not asking for broad explanations
- not scanning the whole codebase when one file suffices
- not producing speculative designs
- not patching unrelated files
- not using broad validation where a focused check is enough

## 8. Practical checklist

Before sending a prompt, ask:

- Do I need this file, or just the relevant function?
- Am I including the error, or only the relevant part?
- Is the task narrow enough?
- Am I asking for too much output?
- What is the smallest validation step?

If the answer is not clear, shrink the task.

## 9. The best habit

The best way to improve Codex efficiency is not to chase bigger prompts. It is to reduce needless context and run tighter feedback loops.

Use an iterative loop:

1. small prompt
2. narrow read
3. patch
4. validate
5. refine prompt
6. repeat

## 10. Core formula

High output quality + low token spend ≈

- narrow task scope
- exact constraints
- minimal context
- structured output
- targeted validation

This is the foundation of a strong Codex workflow.
