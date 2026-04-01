---
name: explain
description: Explain code or concept in depth
tags: [documentation, learning]
---

# Explain

Analyze and explain the selected code or concept in depth, making it easy to understand for both the author and newcomers.

## Objective

Produce a clear, expert-level explanation of the selected code or concept. The reader should walk away understanding *what* the code does, *how* it works, and *why* it was written this way — including trade-offs and non-obvious details.

## Steps

1. **Read and identify scope** — determine whether the selection is a function, class, module, algorithm, or high-level concept. State what you are explaining.
2. **Summarize purpose** — describe the overall intent in one or two sentences.
3. **Walk through the logic** — break the code into logical sections and explain each in order. Highlight control flow, data transformations, and key API calls.
4. **Surface the "why"** — explain design decisions, pattern choices, and any trade-offs (performance vs. readability, generality vs. simplicity, etc.).
5. **Note edge cases and gotchas** — call out inputs or conditions that could cause unexpected behavior, silent failures, or performance cliffs.
6. **Connect to broader context** — mention relevant design patterns, best practices, or related parts of the codebase when it helps understanding.

## Requirements

- Keep the tone technical and concise — no filler or restating the obvious.
- Reference specific lines or code blocks when explaining.
- If the code uses domain-specific concepts (e.g. NMS, alpha blending, backpressure), define them briefly.
- Do not suggest code changes — this is an explanation, not a review.

## Output

1. **Overview** — brief summary of what the code does and its role in the system.
2. **Detailed Breakdown** — section-by-section walkthrough of the logic.
3. **Key Concepts** — patterns, techniques, or principles used (with brief definitions if non-trivial).
4. **Considerations** — edge cases, performance characteristics, or security notes (if applicable).
