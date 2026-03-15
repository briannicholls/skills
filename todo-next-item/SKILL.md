---
name: todo-next-item
description: Read a root TODO checklist, pick the next unchecked item, execute it, and update the checklist.
metadata:
  author: b_five
  version: "1.0.0"
  argument-hint: <optional-path-to-todo-file>
---

# TODO Next Item

Use this skill when the user asks to continue a checklist-driven workflow.

## Default TODO Path

1. If the user supplies a path argument, use it.
2. Otherwise use `TODO.md` in the active project root.
3. If `TODO.md` is missing, check `todo.md`.
4. If still missing, ask for the file path and stop.

## Execution Workflow

1. Read the TODO file.
2. Find the first unchecked checkbox item (`- [ ] ...`) in top-to-bottom order.
3. Treat that item as the active task and execute it end-to-end.
4. When completed, update the same line to checked (`- [x] ...`).
5. If partially completed, keep it unchecked and append a short indented progress note directly below it.
6. Report what was completed, what changed, and the next unchecked item.

## Rules

- Do not reorder checklist items unless the user asks.
- Keep checklist text concise and action-oriented.
- If an item is too large, split it into smaller unchecked sub-items directly beneath it.
- Never mark an item complete without implementing and validating the change.
- Preserve existing checked/unchecked states for unrelated items.
