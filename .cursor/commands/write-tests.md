---
name: write_tests
description: Generate a complete test suite for selected code from scratch
tags: [testing, quality]
---

# Write Tests

Generate a thorough test suite for the selected code, covering happy paths, edge cases, and failure modes — ready to run with no modification.

## Objective

Produce tests that act as a living specification of the code's intended behavior. Tests must be practical and runnable, not illustrative placeholders. The reader should be able to drop the output into the project and execute it immediately.

## Steps

1. **Identify the test runner** — inspect the project for `pytest`, `unittest`, `jest`, `vitest`, or other configurations. Use whatever is already in place. If nothing exists, default to `pytest` for Python and `vitest` for TypeScript/React.
2. **Understand the code under test** — read the selected code carefully. Identify all public functions, classes, and methods. For each, determine:
   - Inputs and their types/constraints
   - Expected outputs or side effects
   - Error conditions and what should be raised/returned
3. **Design the test cases** — for every unit, cover:
   - **Happy path** — typical valid input produces the correct output.
   - **Boundary conditions** — empty collections, zero values, max values, single-element inputs.
   - **Invalid input** — wrong types, out-of-range values, malformed data; assert the correct error is raised.
   - **Side effects** — verify external calls (file writes, DB inserts, HTTP requests) using mocks or fixtures.
4. **Write the tests** — produce a complete, importable test file. Follow the project's existing test conventions (file naming, fixture style, assertion library).
5. **Add fixtures and mocks** — create the minimal setup needed (temp directories, in-memory DBs, patched dependencies) so tests are isolated and reproducible.
6. **Annotate intent** — add a one-line comment above each test explaining *what* behavior it is asserting, not *how*.

## Requirements

- Tests must be self-contained — no manual setup steps outside of the test file itself.
- Use `pytest` fixtures, `unittest.mock`, or the framework's native mocking over ad-hoc monkey-patching.
- Do not test implementation details — test observable behavior only.
- Each test must have a single, clear assertion purpose. Avoid testing multiple unrelated behaviors in one test.
- If the code cannot be tested without significant refactoring (e.g. no dependency injection), note this explicitly and suggest the minimal change needed to make it testable.
- Match the project's existing naming convention (`test_<function>_<scenario>` for Python, `should <behavior>` for JS).

## Output

1. **Test plan** — a brief table mapping each function/class to the test cases that will be generated.
2. **Test file** — the complete, runnable test file with all imports, fixtures, and test functions.
3. **Coverage notes** — explicitly list any behaviors that were intentionally left untested and why (e.g. requires live network, non-deterministic output).
4. **Run command** — the exact command to execute the tests (e.g. `pytest scripts/test_yolo_inference.py -v`).
