---
name: concise-inline-comments
description: Add brief, high-signal inline comments to newly written code for medium-to-large implementations where architecture or intent may be non-obvious.
metadata:
  author: opencode
  version: "1.0.0"
  argument-hint: <optional-scope>
---

# Concise Inline Comments

Use this skill when writing new code and the task is medium to large, broad in scope, or requires architecture decisions.

## When to Apply

Apply comments when:
- The change introduces multiple functions, modules, or data flow steps.
- The request is broad enough that design choices were made during implementation.
- Control flow, invariants, or side effects are not immediately obvious.

Skip comments when:
- The change is small and local.
- The code is self-explanatory from clear naming and structure.
- A comment would only restate the exact code behavior.

## Comment Style

- Keep comments brief and scannable (usually 3-12 words).
- Explain intent, constraints, or rationale (the "why"), not syntax (the "what").
- Place comments directly above the non-obvious block they clarify.
- Use one comment per logical block; avoid line-by-line narration.
- Keep comments current when editing nearby code.

## High-Value Comment Targets

1. Architectural boundaries and handoffs.
2. Non-obvious guards, fallbacks, and branching logic.
3. Ordering requirements, retries, idempotency, or race prevention.
4. Data normalization assumptions and edge-case handling.
5. Security, permission, or trust-boundary checks.
6. Temporary workarounds with removal conditions.

## Avoid

- Obvious comments (for example, `// increment counter`).
- Duplicating function names, types, or signatures in prose.
- Large comment blocks that reduce readability.
- Adding comments to untouched code unless needed for correctness.

## Quick Heuristic

Before adding a comment, ask:
"Will a senior engineer parse this block in under 5 seconds without extra context?"

- If yes, skip the comment.
- If no, add one concise inline comment.

## Output Expectation

For qualifying tasks, include brief inline comments only in newly written or significantly reworked code.
