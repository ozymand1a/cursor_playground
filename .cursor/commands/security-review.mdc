---
name: security_review
description: Comprehensive security review to identify and fix vulnerabilities
tags: [security, review]
---

# Security Review

Perform a comprehensive security audit of the selected code, identifying vulnerabilities and providing concrete fixes.

## Objective

Analyze the code through an attacker's lens. Find exploitable vulnerabilities, insecure defaults, and missing safeguards. Each finding must include a severity rating, a proof-of-concept or attack scenario, and a ready-to-apply fix. The goal is to harden the code without breaking functionality.

## Steps

1. **Map the attack surface** — identify all entry points: user inputs, API endpoints, file uploads, environment variables, CLI arguments, deserialized data, and inter-service communication.
2. **Injection & input validation** — check for SQL injection, command injection, path traversal, XSS, template injection, and LDAP/XML injection. Verify that all external input is validated and sanitized before use.
3. **Authentication & authorization** — review auth flows for bypasses, missing checks, privilege escalation, insecure token handling, and session management issues.
4. **Secrets & configuration** — scan for hardcoded credentials, API keys, tokens, and connection strings. Check that secrets come from environment variables or a vault, not source code.
5. **Data exposure** — look for sensitive data in logs, error messages, HTTP responses, or stack traces. Verify that PII and secrets are masked or omitted.
6. **Cryptography** — flag weak algorithms (MD5, SHA1 for security, ECB mode), insufficient key lengths, missing salts, and custom crypto implementations.
7. **Dependency risks** — check for known vulnerable dependencies, pinned-to-outdated versions, and unnecessary packages that increase the attack surface.
8. **File & resource handling** — review file operations for path traversal, unsafe temp file creation, unrestricted upload types/sizes, and missing resource limits (memory, CPU, connections).
9. **Race conditions & TOCTOU** — identify time-of-check-to-time-of-use issues, especially in file operations, permission checks, and shared state access.

## Requirements

- Reference specific lines or code blocks for each finding.
- Classify each finding by severity: **critical**, **high**, **medium**, or **low**.
- Include a brief attack scenario explaining how the vulnerability could be exploited.
- Provide a concrete fix (code snippet) for each finding — not just a description.
- Do not flag theoretical issues that are unexploitable in the code's actual context.
- If no vulnerabilities are found, state that explicitly with a summary of what was checked.

## Output

1. **Threat summary** — one-paragraph overview of the security posture and the most urgent risk.
2. **Findings** — a numbered list, each containing:
   - Severity tag (`critical` / `high` / `medium` / `low`)
   - Vulnerability type (e.g. SQL injection, path traversal)
   - Attack scenario (one or two sentences)
   - Affected code (reference specific lines)
   - Suggested fix (before/after code snippets)
3. **Hardening recommendations** — additional defensive measures worth adopting (e.g. CSP headers, rate limiting, input allow-lists) even if no direct vulnerability was found.
