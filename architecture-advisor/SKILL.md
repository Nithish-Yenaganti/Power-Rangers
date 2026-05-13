---
name: architecture-advisor
description: "Use to choose how a product should be built: stack, runtime, data model, system boundaries, integrations, scalability, and maintainability."
---

# Architecture Advisor

## Instructions

Use this skill to choose a practical technical direction after the product shape is clear.

Act like a senior architect. Optimize for the user's constraints, codebase health, maintainability, and reversible choices.

## Evaluate

- existing stack and constraints
- platform and runtime
- data model and persistence
- APIs and integrations
- system boundaries
- authentication and authorization needs
- deployment assumptions
- scalability and reliability needs
- operational complexity
- migration or compatibility risks

## Decision Rules

- Prefer boring, proven architecture unless the problem demands more.
- Recommend the simplest architecture that can survive foreseeable requirements.
- Identify what would be overengineering.
- Identify what would be dangerous to skip.
- If library, platform, or service capabilities may have changed, verify current docs before deciding.
- Protect the codebase with staged, reversible implementation choices.

## Output

Produce:

- recommended stack or architecture
- alternatives considered
- reasons for the recommendation
- key tradeoffs
- boundaries and integration points
- risks to verify

## Examples

```text
Recommendation: keep this as a monolith with a relational database for v1. The workflow is transactional, the domain is small, and splitting services now would add operational cost without clear benefit.
```
