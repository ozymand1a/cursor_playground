---
name: code_review
description: Thorough code review for functionality, maintainability, and security
tags: [review, quality]
---

# Code Review

Perform a thorough code review of the selected code, verifying functionality, maintainability, and security before approving a change.

## Objective

Analyze the code as a senior reviewer would in a pull request. Identify bugs, design flaws, security risks, and readability issues. Provide concrete, actionable feedback — not vague suggestions. The goal is to catch problems early and raise the overall quality of the codebase.

## Steps

1. **Understand intent** — read the code and infer what it is trying to accomplish. State your understanding in one sentence so the author can confirm.
2. **Correctness** — trace the logic for both happy paths and edge cases. Look for off-by-one errors, unhandled exceptions, race conditions, and incorrect assumptions about input.
3. **Architecture & design** — evaluate separation of concerns, coupling, abstraction level, and adherence to the project's existing patterns. Flag over-engineering as well as under-engineering.
4. **Readability** — check naming, function length, nesting depth, and whether the code is self-documenting. Note any spots where a comment or rename would eliminate confusion.
5. **Performance** — identify unnecessary allocations, redundant loops, N+1 queries, or anything that would degrade at scale.
6. **Security** — look for injection vectors, improper input validation, hardcoded secrets, unsafe deserialization, and missing access checks.
7. **Testing** — assess whether the change is testable and whether existing tests cover the new behavior. Suggest specific test cases if coverage is lacking.

## Requirements

- Reference specific lines or code blocks when raising an issue.
- Classify each finding by severity: **critical**, **warning**, or **nit**.
- Keep suggestions concrete — show the improved code, not just a description of what to change.
- Do not flag style preferences that have no impact on correctness or readability.
- If the code is clean, say so — don't invent issues to fill space.

## Output

1. **Summary** — one-paragraph verdict: approve, request changes, or needs discussion.
2. **Findings** — a numbered list of issues, each containing:
   - Severity tag (`critical` / `warning` / `nit`)
   - Description of the problem
   - Suggested fix (code snippet when applicable)
3. **Positive notes** — highlight anything well done (good abstractions, thorough error handling, clean naming, etc.).
