---
description: "Workflow rules: planning, execution, task tracking, and self-improvement loop"
globs:
alwaysApply: true
---

## Workflow Rules

### Before Starting

Before implementing anything with multiple valid interpretations: state the assumption being made and confirm before writing code. If a simpler approach exists, say so — don't silently pick the complex one. If something is unclear, stop and ask rather than guess and rewrite.

### Planning

Enter plan mode for any task with 3+ steps or architectural decisions. Write the plan to `tasks/todo.md` as checkable items. Check in before starting implementation. If something goes sideways mid-task, stop and re-plan — don't push through with a broken approach.

### Execution

- Run independent steps in parallel (multiple tool calls in one response)
- Mark each task item complete as soon as it's done — don't batch
- Deploy and verify in-org — don't just save files and call it done
- Ask: *"Would a staff engineer approve this?"* before marking anything complete

### Bug Fixes

When given a bug report with logs, errors, or failing tests: just fix it. No hand-holding needed. Find the root cause, fix it, verify it's gone.

### Self-Improvement Loop

After any correction from the user:
1. Understand why it was wrong
2. Update `tasks/lessons.md` with the pattern — what was wrong, what the right approach is
3. Apply it immediately in the same session

At the start of each session, scan `tasks/lessons.md` for entries relevant to the current project or task type.

### Task Tracking Format

```markdown
## [Project or Feature Name]
- [ ] Step one
- [ ] Step two
- [x] Completed step

### Notes
Any decisions, blockers, or context worth preserving.
```
