---
name: same-page
description: "Use for clarification-first planning before implementation: align requirements, scope, stack, architecture, risks, and execution plan before code is written."
---

# Same Page

## Instructions

Use this skill when the user is still forming an idea and wants shared understanding before implementation.

The goal is to reach explicit alignment on what is being built, how it should work, what constraints apply, what stack and architecture make sense, and what the execution path should be.

Do not write code, edit files, or run implementation commands during this phase.

## Default Mode

Stay in discovery and clarification mode until the user and the agent are aligned.

Treat these as preconditions for implementation:

1. The problem is clearly stated.
2. The desired behavior is concrete.
3. Scope and non-goals are defined.
4. Constraints and assumptions are visible.
5. Tech stack choices are discussed.
6. Architecture and system boundaries are discussed.
7. Open questions are resolved or explicitly parked.
8. The user confirms that you are on the same page.

Only after that, create a plan.

## Hard Rules

- Do not implement code while this skill is active and alignment is still incomplete.
- Do not silently jump from idea discussion to execution.
- Do not produce a build plan before the core idea, constraints, and architecture are clear enough to defend.
- Ask targeted questions when ambiguity would change architecture, stack, scope, UX, data model, or rollout strategy.
- Make reasonable synthesis attempts instead of asking endless questions. The point is convergence, not interrogation.

## Conversation Workflow

### 1. Frame The Idea

Start by restating the idea in sharper terms:

- what problem this solves
- who it is for
- what success looks like
- what is still unclear

If the user is vague, convert the idea into a concrete working interpretation and ask the user to confirm or correct it.

### 2. Extract The Product Shape

Work toward clarity on:

- primary user flow
- key features
- inputs and outputs
- edge cases
- constraints
- non-goals

Keep this practical. Prefer specific behavior over abstract aspirations.

### 3. Decide The Technical Direction

Before planning implementation, align on:

- tech stack
- platform and runtime
- data model or storage needs
- external integrations
- system boundaries
- architecture style
- deployment assumptions

If multiple options are viable, compare them briefly and recommend one with reasons.

### 4. Surface Risks And Unknowns

Call out what could materially change the solution:

- unclear requirements
- scaling assumptions
- security/privacy concerns
- cost constraints
- migration complexity
- operational burden

Separate facts from assumptions.

### 5. Confirm Shared Understanding

Before any plan, provide a compact alignment summary covering:

- objective
- scope
- chosen stack
- architecture direction
- major constraints
- unresolved items

Ask for confirmation only when needed. If the user has already confirmed, move on.

### 6. Plan Only After Alignment

Once the user confirms the summary is correct, create an implementation plan.

The plan should include:

- phases
- sequencing
- dependencies
- major technical milestones
- validation points

Do not start implementation unless the user asks for it after planning.

## Response Style

- Be structured, calm, and concrete.
- Push toward precision when the user is hand-wavy.
- Prefer synthesis over long brainstorming dumps.
- Challenge weak assumptions directly but briefly.
- Keep the discussion anchored to decisions that affect implementation.

## Useful Prompts To Drive Alignment

Use questions like these when needed:

- What is the exact problem we are solving?
- Who is the first real user?
- What should happen step by step in the main flow?
- What is explicitly out of scope for v1?
- What constraints matter most: speed, cost, simplicity, scale, or reliability?
- Does this need to be optimized for fast shipping or long-term extensibility?
- What stack do you already want to keep or avoid?
- What architecture would be overkill here?

## Examples

```text
User: I want to build a dashboard for my team.
Agent: Before planning implementation, let's align on the dashboard users, main decisions it supports, data sources, must-have views, stack constraints, and what is out of scope for v1.
```

```text
User: Make me an app for invoices.
Agent: Working interpretation: a small invoice app for creating, tracking, and exporting invoices. Key choices still needed: target platform, user roles, storage, payment integration, PDF/email needs, and v1 scope.
```

## Exit Condition

This skill is complete when:

1. The agent can summarize the idea, behavior, stack, architecture, and constraints clearly.
2. The user confirms that summary is accurate.
3. A plan can be created without guessing at fundamentals.
