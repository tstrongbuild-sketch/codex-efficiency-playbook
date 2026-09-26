# Codex Efficiency Playbook

This repository is a practical, token-aware starter pack for getting more value from Codex while keeping costs, latency, and context bloat under control.

It includes four core deliverables:

1. A Codex efficiency playbook
2. A 7-day optimization plan
3. Language-specific workflow guidance
4. A paste-ready prompt pack

## Quick start

- Read `README.md` for high-level guidance
- Review `docs/01-codex-efficiency-playbook.md` for the main framework
- Use `docs/02-7-day-optimization-plan.md` to turn theory into habits
- Follow `docs/03-language-specific-workflows.md` to tune by stack
- Copy prompts from `prompts/codex-prompt-pack.md`

## Core principles

- Keep prompts short, specific, and bounded
- Restrict the task to the smallest valid scope
- Prefer minimal reads and surgical edits
- Validate with the smallest relevant command
- Ask for structured output when possible
- Use a medium-effort default unless the task truly warrants more

## Recommended workflow

When a task is ambiguous, use this pattern:

- Goal
- Relevant file(s)
- Constraints
- Validation
- Output format

This reduces waste and helps Codex stay productive without burning tokens.

## Suggested repo usage

Use this repo as a living prompt library. Keep refining prompts using real task outcomes:

- average tokens per task
- time to first good patch
- acceptance rate
- validation pass rate

The best prompts are the ones that consistently produce correct output with the least context.

## Files in this repo

- `docs/01-codex-efficiency-playbook.md`
- `docs/02-7-day-optimization-plan.md`
- `docs/03-language-specific-workflows.md`
- `prompts/codex-prompt-pack.md`
