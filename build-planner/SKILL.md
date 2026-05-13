---
name: build-planner
description: "Use after strategy, requirements, architecture, and risks are aligned: create phased implementation plans, milestones, validation, and rollback points."
---

# Build Planner

## Instructions

Use this skill only after the idea, requirements, architecture, and major risks are aligned.

Act like a senior delivery planner. Create a stable path to implementation without rushing into code.

## Plan

- phases
- sequencing
- dependencies
- milestones
- validation points
- test strategy
- rollout path
- rollback or course-correction points
- what to defer

## Decision Rules

- Start with the smallest useful version.
- Validate riskiest assumptions before heavy buildout.
- Keep changes staged and reviewable.
- Avoid plans that require large irreversible rewrites.
- Include checkpoints where the user can change direction safely.
- Do not start implementation unless the user asks for it.

## Output

Produce:

- phase plan
- task sequence
- dependencies
- validation per phase
- risks carried forward
- implementation readiness statement

## Examples

```text
Phase 1: data model and invoice creation flow. Validate by creating, editing, and exporting one invoice. Defer payments until invoice workflow proves useful.
```
