---
name: build-planner
description: "Use after strategy, requirements, architecture, and risks are aligned: create phased implementation plans, milestones, validation, and rollback points."
---

# Build Planner

## Instructions

Plan the build only after strategy, requirements, architecture, and risks are clear. Make the path small, sequenced, testable, and hard to derail. Do not create a giant roadmap. Do not start with polish. Start with the smallest useful proof.

Each phase must have a purpose, exit check, and rollback point. Defer anything that does not validate the product, reduce risk, or unlock the next phase.

## Output

Produce an **Execution Plan**:

- phase
- goal
- tasks
- dependencies
- validation check
- tests
- risks carried forward
- rollback or course-correction point
- deferred work
- readiness verdict

## Examples

```text
Phase 1: create invoice draft flow. Exit check: user can create, edit, save, and export one valid invoice.
```
