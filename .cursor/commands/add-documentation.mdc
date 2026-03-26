---
name: add_documentation
description: Add comprehensive documentation for code or features
tags: [documentation, docs]
---

# Add Documentation

Generate clear, comprehensive documentation for the selected code or feature and place it in the appropriate location.

## Objective

Produce documentation that lets a new developer understand, use, and contribute to the code without reading every line. Detect the project's existing documentation style (docstrings, README, `/docs` folder, JSDoc, etc.) and follow it. If no convention exists, use the most idiomatic format for the language. Documentation must be concise — thorough but never redundant.

## Steps

1. **Determine scope and placement** — decide what needs documenting (module, class, function, feature, CLI tool) and where the docs belong:
   - **Inline** — docstrings / JSDoc / type hints for individual functions, classes, and methods.
   - **README** — high-level purpose, quickstart, and usage examples for the project or package.
   - **Docs folder** — architecture, design decisions, and extended guides for larger features.
   - Place docs where the project already keeps them; create a new location only if nothing exists.

2. **Write the "What & Why"** — for each documented unit, cover:
   - What it does (one sentence).
   - Why it exists — the problem it solves or the design constraint it satisfies.
   - Key concepts or domain terms a reader might not know.

3. **Document the API surface** — for every public function, class, or endpoint:
   - Signature with typed parameters and return value.
   - Description of each parameter (type, default, constraints).
   - Return value semantics.
   - Exceptions / errors raised and when.
   - A minimal usage example (runnable where possible).

4. **Explain architecture and design decisions** — for modules or features:
   - How the parts fit together (data flow, component relationships).
   - Important design choices and their trade-offs.
   - Dependencies and integration points.

5. **Add examples** — provide at least one realistic usage example per documented unit. Include edge-case examples where behavior is non-obvious.

6. **Note pitfalls and best practices** — document known gotchas, common misuses, and recommended patterns in a short section.

## Requirements

- Match the project's existing doc format and style. Do not introduce a new convention without reason.
- Use the language's idiomatic doc format: Python → docstrings (Google/NumPy style), JS/TS → JSDoc, Go → godoc comments, Rust → `///` doc comments, etc.
- Keep each description as short as it can be while remaining unambiguous. Prefer a clear example over a long explanation.
- Every code example must be syntactically correct and runnable in context.
- Do not document the obvious — skip trivial getters, self-explanatory one-liners, and boilerplate.
- If the code is already well-documented, state that and suggest only incremental improvements.

## Output

1. **Documentation plan** — a short list of what will be documented and where each piece goes.
2. **Generated documentation** — the actual docs, ready to be inserted (docstrings inline, markdown for README/docs).
3. **Checklist** — confirm coverage of:
   - Purpose and motivation
   - API signatures, parameters, and return values
   - Usage examples
   - Error handling and edge cases
   - Architecture notes (if applicable)
   - Pitfalls and best practices (if applicable)
