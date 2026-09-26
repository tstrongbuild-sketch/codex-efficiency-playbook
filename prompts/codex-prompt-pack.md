# Codex Prompt Pack

This file contains paste-ready prompts that are designed to reduce waste and improve code generation quality.

## 1. Bug fix prompt

> Act as a senior engineer. Fix the bug in `<file_or_module>`. Only inspect the exact files needed to diagnose this issue. Keep the patch minimal and surgical. Do not refactor unrelated code. Use the existing patterns in the repo. Validate with the smallest relevant command. Return: 1) root cause 2) patch summary 3) validation command.

## 2. Feature implementation prompt

> Implement `<feature_name>` in `<file_or_module>`. Keep the scope narrow and aligned with the existing architecture. Do not add speculative features. Prefer minimal, idiomatic code. Validate with the smallest relevant command. Return: implementation summary, files changed, and validation step.

## 3. Test generation prompt

> Write the smallest relevant test for `<behavior_or_bug>`. Use the repo’s existing testing style and framework. Cover only the required behavior. Do not add broad test scaffolding. Return the test name, key assertions, and the exact command to run.

## 4. Refactor prompt

> Refactor `<module_or_function>` only as much as needed to improve maintainability without changing behavior. Keep the refactor surgical. Preserve the public contract. Do not rename things unnecessarily. Return the change summary and the minimal validation command.

## 5. Code review prompt

> Review the code in `<file_or_patch>` for correctness, maintainability, and edge cases. Focus on likely issues introduced by this change. Ignore style-only comments unless they affect correctness or clarity. Return: findings, severity, affected file/area, and a concise recommendation.

## 6. API contract fix prompt

> Fix the bug related to `<API contract / behavior>` in `<file>`. Preserve the request/response contract unless the issue requires a minimal, explicit change. Keep the patch local and validated. Return the root cause, patch summary, and validation command.

## 7. Narrow context prompt

> You are working on a repo. Diagnose and fix `<issue>` using the minimal context required. Read only the targeted files and symbols. Do not inspect the full repo unless necessary. Keep the patch minimal and explain only the root cause and fix.

## 8. Minimal-output prompt

> Fix `<issue>` with the smallest possible patch. Do not explain at length. Return only: root cause, changed files, validation command.

## 9. High-confidence prompt

> Act as a senior engineer. Fix `<issue>` with a minimal, production-quality patch. Include only the exact files needed. Keep the patch consistent with the repo’s conventions. Validate with a targeted command and report any assumptions or risks.

## 10. Strong default prompt

> Act as a senior engineer. Fix the issue in `<file_or_module>`.
>
> Scope:
> - inspect only the relevant files and symbols
> - keep the patch minimal
> - do not refactor unrelated areas
> - preserve the existing architecture and conventions
>
> Constraints:
> - no speculative features
> - no broad cleanup
> - validate with the smallest relevant command
>
> Output:
> 1) root cause
> 2) patch summary
> 3) validation command
> 4) any risk or assumption

## Prompt tuning rule

If a prompt takes more than one round to converge, reduce the scope, tighten the constraints, or remove unnecessary context. Usually the first path to a better answer is narrower, not longer.
