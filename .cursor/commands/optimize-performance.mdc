---
name: optimize_performance
description: Analyze code for performance bottlenecks and provide optimization recommendations
tags: [performance, optimization]
---

# Optimize Performance

Analyze the selected code for performance bottlenecks and provide optimization recommendations with measurable impact, while preserving code quality and readability.

## Objective

Identify concrete performance issues in the selected code — slow algorithms, wasteful allocations, redundant I/O, poor concurrency usage — and propose targeted fixes. Each recommendation must explain the expected speedup and any trade-offs involved. The goal is real, measurable improvement, not micro-optimization.

## Steps

1. **Profile mentally** — read through the code and identify the hot path. Determine what runs once vs. what runs per-item, per-frame, or per-request.
2. **Algorithmic complexity** — check for suboptimal time/space complexity. Flag O(n²) patterns that can be O(n), redundant sorts, or repeated lookups that should use a hash map.
3. **Memory & allocations** — find allocations inside loops (object creation, list/array copies, string concatenation). Suggest pre-allocation, object reuse, or buffer pooling where applicable.
4. **I/O & network** — identify blocking I/O on the critical path, sequential operations that could be parallelized, and missing caching or batching opportunities.
5. **CPU↔GPU / serialization boundaries** — flag unnecessary data transfers (`.cpu()`, `.cuda()`, `.item()`, serialization/deserialization) inside hot loops.
6. **Concurrency & parallelism** — assess whether the workload benefits from threading, multiprocessing, async I/O, or batch processing, and suggest the appropriate approach.
7. **Standard library & ecosystem wins** — identify cases where a built-in or well-known library function would outperform the hand-rolled implementation (e.g. `numpy` vectorization over Python loops, `itertools` over manual iteration).

## Requirements

- Reference specific lines or code blocks for each finding.
- Classify each recommendation by expected impact: **high**, **medium**, or **low**.
- Show the optimized code alongside the original for each recommendation.
- Do not sacrifice readability for marginal gains — flag when an optimization is not worth the complexity.
- If the code is already well-optimized, say so explicitly.

## Output

1. **Assessment** — one-paragraph summary of overall performance characteristics and the most impactful bottleneck.
2. **Recommendations** — a numbered list, each containing:
   - Impact tag (`high` / `medium` / `low`)
   - Description of the bottleneck
   - Before/after code snippets
   - Estimated improvement and any trade-offs
3. **Quick wins** — a short list of low-effort changes that can be applied immediately.
