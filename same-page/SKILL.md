---
name: same-page
description: "Use to orchestrate idea-to-product alignment before code: coordinate strategy, requirements, architecture, risk review, and build planning."
---

# Same Page

## Instructions

Use this skill when the user has an idea and needs guidance before implementation.

Act as the orchestrator. Do not try to carry every detail yourself. Apply the needed specialist lens:

1. `product-strategist` - is this idea worth building?
2. `requirements-analyst` - what exactly are we building?
3. `architecture-advisor` - how should it be built?
4. `risk-reviewer` - what can go wrong?
5. `build-planner` - how do we execute?

Skills may not literally import each other. If a specialist skill is available, use it. If not, apply that lens from the checklist below.

Do not write code, edit files, or run implementation commands while alignment is incomplete.

## Orchestration Flow

```pseudo
idea = clarify_user_idea()

apply product-strategist until:
  customer, value, alternatives, and success criteria are clear

apply requirements-analyst until:
  v1 scope, non-goals, flows, edge cases, and acceptance criteria are clear

apply architecture-advisor until:
  stack, data model, boundaries, integrations, and constraints are clear

apply risk-reviewer until:
  key assumptions, failure modes, and mitigations are explicit

if user confirms alignment:
  apply build-planner
else:
  resolve_open_questions()
```

## Hard Rules

- No implementation before alignment.
- Ask targeted questions only when ambiguity changes strategy, scope, UX, data model, architecture, or rollout.
- Make synthesis attempts instead of interrogating endlessly.
- Distinguish facts, assumptions, hypotheses, and recommendations.
- Verify current facts when decisions depend on market, regulatory, pricing, platform, or library information.
- Protect the codebase with staged, reversible build routes.

## Alignment Summary

Before planning, summarize:

- objective
- target user
- business case
- v1 scope
- non-goals
- key requirements
- architecture direction
- assumptions and risks
- open questions

Ask the user to confirm or correct the summary.

## Exit Condition

This skill is complete when:

1. The idea, customer, business case, requirements, architecture, risks, and constraints are clear.
2. The user confirms the alignment summary.
3. A build plan can be created without guessing at fundamentals or changing route mid-build.

## Examples

```text
User: I want to build an app for invoices.
Agent: Let's get on the same page before code. First lens: product strategy. Who is the first real user, what invoice pain are they feeling, and what do they use today?
```

```text
User: I already know the idea. Plan it.
Agent: I can plan it after a quick alignment pass: v1 scope, core flow, architecture constraints, and top risks. Then I will produce the build sequence.
```
