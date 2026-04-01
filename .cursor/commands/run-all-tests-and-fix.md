---
name: run_all_tests_and_fix
description: Execute the full test suite and systematically fix any failures
tags: [testing, fix, quality]
---

# Run All Tests & Fix

Execute the project's full test suite, analyze every failure, and fix the underlying issues until all tests pass.

## Objective

Run the complete test suite, capture the output, and systematically resolve each failure. Fixes must address the root cause in the source code — not patch or weaken the tests — unless a test is genuinely wrong. The session ends when the full suite passes cleanly.

## Steps

1. **Discover the test runner** — inspect the project for `pytest`, `unittest`, `jest`, `vitest`, `go test`, or other test configurations. Use the runner that the project already uses.
2. **Run the full suite** — execute all tests and capture the output. Note the total count, pass count, fail count, and error count.
3. **Triage failures** — group failures by root cause (e.g. a single broken import may cause dozens of failures). Prioritize by dependency order: fix foundational issues first.
4. **Fix each root cause** — for every distinct issue:
   - Read the failing test to understand the expected behavior.
   - Read the relevant source code.
   - Apply the minimal fix that satisfies the test without breaking other functionality.
5. **Re-run after each fix** — run the suite again to confirm the fix resolved the targeted failures and introduced no regressions.
6. **Repeat** — continue the triage → fix → verify cycle until the full suite passes.

## Requirements

- Fix source code to match tests, not the other way around. Only modify a test if it is demonstrably incorrect (wrong assertion, outdated expectation, flaky timing).
- Keep fixes minimal and focused — do not refactor unrelated code during this process.
- If a fix has side effects on other tests, address them in the same cycle before moving on.
- Preserve existing code style and conventions.
- If a failure is caused by a missing dependency or environment issue, report it clearly instead of guessing.

## Output

1. **Initial run summary** — test runner used, total / passed / failed / errored counts.
2. **Fix log** — for each fix applied:
   - Failing test name(s)
   - Root cause (one sentence)
   - What was changed and where
3. **Final run summary** — confirmation that all tests pass, with the full pass count.
4. **Notes** — any flaky tests, skipped tests, or environmental concerns encountered along the way.
