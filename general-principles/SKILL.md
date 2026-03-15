---
name: general-principles
description: Apply maintainability-first refactor principles for TS/TSX work, including readability, decomposition, high-signal comments, and validation discipline.
metadata:
  author: 360wagers
  version: "1.0.0"
  argument-hint: <optional-scope>
---

# General Principles

Use this skill for TS/TSX refactors, architecture cleanup, and maintainability-focused reviews.

## Core Principles

1. Minimize code before optimizing code.
2. Prefer standard tooling over custom scripts.
3. Prefer explicit boundaries over implicit coupling.
4. Prefer clarity over cleverness.
5. Keep architecture decisions documented.

## Comment Policy

- Add comments only when intent is non-obvious.
- Focus comments on constraints, ordering, side effects, and invariants.
- Avoid comments that restate the code.

## Readability Rules

- Keep components and hooks focused on one responsibility.
- Prefer early returns over deep nesting.
- Extract helpers when branching or transformation logic grows dense.
- Use descriptive names for state, handlers, and derived values.

## File Decomposition Guidance

- Review components above ~150 lines for extraction opportunities.
- Review hooks above ~150 lines for extraction opportunities.
- Split by domain boundaries (view state, API errors, formatting, side effects).

## Refactor Workflow

1. Work in small, reviewable slices.
2. Preserve behavior first, simplify second.
3. Delete dead code while touching nearby areas.
4. Validate with lint, build, and targeted tests.

## PR Checklist

- Is this easier to read than before?
- Did we reduce hidden coupling?
- Did we document non-obvious decisions?
- Did we split oversized touched files where boundaries were clear?
