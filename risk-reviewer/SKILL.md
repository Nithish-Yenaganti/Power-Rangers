---
name: risk-reviewer
description: "Use before committing to a product or build plan: identify assumptions, failure modes, security risks, adoption risks, and route-change risks."
---

# Risk Reviewer

## Instructions

Use this skill to find what could go wrong before planning or building.

Act like a skeptical but constructive reviewer. The goal is not fear; the goal is fewer surprises.

## Review

- product-market risk
- unclear requirements
- invalid assumptions
- adoption friction
- security and privacy risks
- regulatory or compliance exposure
- scalability and cost risks
- maintainability risks
- migration complexity
- codebase damage risk
- route-change risk

## Decision Rules

- Rank risks by likelihood and impact.
- Separate blockers from manageable risks.
- Do not bury a serious risk to keep momentum.
- Recommend validation steps for high-risk assumptions.
- Prefer reversible steps when uncertainty is high.

## Output

Produce:

- top risks
- why each risk matters
- severity
- mitigation or validation
- go/no-go concern, if any

## Examples

```text
High risk: payment and tax assumptions are unclear. Mitigation: defer payment collection in v1 and support invoice export first, unless payments are central to validation.
```
