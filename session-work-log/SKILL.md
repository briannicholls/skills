---
name: session-work-log
description: Capture a concise session summary and append it to a project log file. Use when asked to "log this session", "save what we did", "create handoff notes", or at the end of substantial coding work.
metadata:
  author: b_five
  version: "1.0.0"
  argument-hint: <optional-log-file-path>
---

# Session Work Log

Create a structured session summary and persist it to a markdown log in the current project.

## Default Log Location

- Use `.claude/session-work-log.md` in the active project root.
- If the user provides a path argument, use that path instead.

## What To Record

Capture only relevant engineering context:

1. Date/time (local) and project/repo name.
2. User request in 1-2 lines.
3. What was changed (feature/fix/refactor/docs/tests).
4. Key files touched.
5. Validation performed (build/tests/lint) and outcome.
6. Important decisions, assumptions, or tradeoffs.
7. Outstanding items / risks.
8. Suggested next steps.

## Required Format

Append a new markdown section using this structure:

```md
## YYYY-MM-DD HH:mm - <short title>

**Request**
- ...

**Completed**
- ...

**Files**
- `path/to/file`

**Validation**
- `command` - pass/fail/not run

**Decisions**
- ...

**Open Items**
- ...

**Next Steps**
- ...
```

## Behavior Rules

- Keep entries concise and factual.
- Do not include secrets, tokens, credentials, or private keys.
- If no validation was run, explicitly write `not run`.
- If no open items remain, write `- None`.
- Always append; do not rewrite previous entries unless explicitly requested.
