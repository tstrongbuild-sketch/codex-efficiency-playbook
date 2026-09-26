# 7-Day Codex Optimization Plan

The goal is to turn token-awareness into a repeatable habit and measure which prompts give the best value.

## Day 1 — Baseline your current workflow

- Pick 3 representative tasks
- Capture
  - prompt length
  - total time to result
  - final quality score
  - validation used
- Note where extra context caused churn

Outcome:
- You have a baseline and a benchmark for improvement.

## Day 2 — Standardize your task template

Create a default task format:

- goal
- relevant file(s)
- constraints
- expected output
- validation command

Use it for bug fixes, small features, and refactors.

Outcome:
- More consistent prompts across tasks.

## Day 3 — Reduce context waste

Audit the last 3 prompts you sent and identify:

- unrelated code pasted
- repeated instructions
- noisy logs
- too broad a task definition

Rewrite each one more narrowly.

Outcome:
- Smaller prompt sizes without loss of correctness.

## Day 4 — Introduce output constraints

Ask for structured outputs such as:

- root cause
- files touched
- validation command
- risk

This keeps the response compact and increases actionability.

Outcome:
- Better signal-to-token ratio.

## Day 5 — Measure validation efficiency

For the same tasks, compare:

- broad test suite vs. targeted validation
- explanation-heavy output vs. concise output
- one-file fix vs. multi-file patch

Outcome:
- Understand the minimum validation needed for confidence.

## Day 6 — Build a reusable prompt library

Create 5 prompt templates:

- bug fix
- feature implementation
- test generation
- refactor safely
- code review

Keep them short and reusable.

Outcome:
- Less prompt friction and less repeated explanation.

## Day 7 — Optimize for your personal ratio

Evaluate which prompt patterns best fit your work:

- fastest completion
- lowest token burn
- highest acceptance rate
- best validation coverage

Select your “golden path” prompt and reuse it for daily work.

Outcome:
- A repeatable Codex workflow tuned to your actual repo and tasks.

## Tracking scorecard

Track these weekly metrics:

- prompt length (tokens or rough char count)
- time to patch
- time to validation
- accepted vs. rejected output
- number of revisits required

This gives you a practical signal for which prompt patterns are worth keeping.

## Day-to-day rule

If a prompt needs more than one correction loop, shrink the task or clarify the scope before retrying.

That is usually the quickest path to lower cost and better output.
