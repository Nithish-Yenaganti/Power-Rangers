# PowerRangers Skills

PowerRangers is a Claude/Codex-compatible skill set for turning rough ideas into product decisions before implementation begins.

The goal is simple: no code before the idea survives strategy, requirements, architecture, risk, and execution planning.

## Repository Status

This is a reusable skill-pack repository. It is intentionally small: the primary source files are the `SKILL.md` instructions in each skill folder.

## Skills

```text
product-strategist/
└── SKILL.md

requirements-analyst/
└── SKILL.md

architecture-advisor/
└── SKILL.md

risk-reviewer/
└── SKILL.md

build-planner/
└── SKILL.md
```

No orchestrator skill is included. Skills do not reliably import or call other skills, so each skill stands alone and triggers from its own description.

## Recommended Sequence

Use the skills in this order when shaping a product:

1. `product-strategist` - decide whether the idea is worth building.
2. `requirements-analyst` - define exactly what ships in v1.
3. `architecture-advisor` - choose the build shape that will not trap the team.
4. `risk-reviewer` - expose what can break the product or plan.
5. `build-planner` - create the execution route after alignment.

The agent may skip ahead only when earlier decisions are already clear.

## Skill Outputs

`product-strategist` produces a **Product Thesis**: customer, pain, wedge, success metric, and verdict.

`requirements-analyst` produces a **Requirements Contract**: v1 scope, user flow, entities, non-goals, and acceptance criteria.

`architecture-advisor` produces an **Architecture Decision Record**: stack, boundaries, tradeoffs, scaling limits, and migration risk.

`risk-reviewer` produces a **Risk Register**: blockers, warnings, mitigations, validation steps, and accepted risks.

`build-planner` produces an **Execution Plan**: phases, dependencies, validation checks, tests, rollback points, and deferred work.

## Compatibility

All skills follow the shared Claude/Codex-friendly structure:

- folder name matches `name`
- file is named `SKILL.md`
- YAML frontmatter includes `name` and `description`
- names use lowercase letters and hyphens
- descriptions are under 200 characters
- body uses plain Markdown
- instructions, output format, and examples are included

## Install

### Claude.ai

Zip the skill folders so they are inside the archive:

```text
power-rangers-skills.zip
├── product-strategist/
│   └── SKILL.md
├── requirements-analyst/
│   └── SKILL.md
├── architecture-advisor/
│   └── SKILL.md
├── risk-reviewer/
│   └── SKILL.md
└── build-planner/
    └── SKILL.md
```

Then:

1. Open `Customize > Skills`.
2. Upload the zip file.
3. Enable the skills.

Claude uses each skill's `description` field to decide when to activate it.

### Claude Code

Personal install:

```sh
mkdir -p ~/.claude/skills
cp -R product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.claude/skills/
```

Project install:

```sh
mkdir -p .claude/skills
cp -R product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner .claude/skills/
```

Restart Claude Code, then ask:

```text
What Skills are available?
```

### Codex

Install in your Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.codex/skills/
```

Restart Codex so it reloads available skills. If your Codex client uses a repo-local skill directory, copy the skill folders there instead.

## ChatGPT.com Fallback

ChatGPT.com does not install `SKILL.md` folders as native Agent Skills in the same way. Use one of these instead:

- Custom Instructions
- Project Instructions
- Custom GPT instructions

Compact instruction:

```text
Before implementation, move through product strategy, requirements, architecture, risk review, and build planning. Do not write code until the idea is concrete enough to build without guessing at fundamentals.
```

## Testing

Product strategy trigger:

```text
Is my invoice app idea worth building for freelance designers?
```

Expected behavior: a Product Thesis with a verdict and riskiest assumption.

Requirements trigger:

```text
Define v1 requirements for an invoice app for freelance designers.
```

Expected behavior: a Requirements Contract with scope, non-goals, and acceptance criteria.

Build planning trigger:

```text
Plan the implementation after strategy, requirements, architecture, and risks are aligned.
```

Expected behavior: an Execution Plan with phases, validation checks, and rollback points.

## Notes

Skills are instruction packages, not system-level rules. They activate when the agent selects them based on the `description`, and they remain lower priority than system/developer instructions.
