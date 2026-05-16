# PowerRangers Skills

PowerRangers is a Claude/Codex-compatible skill set for turning an idea into product decisions before implementation begins.

The goal is to stop agents from rushing into code with unclear requirements, weak assumptions, unstable architecture, or a build route that will collapse halfway through.

## Skills

```text
same-page/
└── SKILL.md

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

No scripts, references, assets, or extra config files are required.

## Same Page System

`same-page` is the orchestrator. It forces one clean route before code: product thesis, requirements contract, architecture decision, risk register, and execution plan.

It coordinates these specialist lenses:

- `product-strategist` - is this idea worth building?
- `requirements-analyst` - what exactly are we building?
- `architecture-advisor` - how should it be built?
- `risk-reviewer` - what can go wrong?
- `build-planner` - how do we execute?

The system is alignment-first: understand the product, challenge the weak parts, choose a stable route, then plan implementation.

## Specialist Skills

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
- instructions and examples are included

## Install

### Claude.ai

Zip the skill folders so they are inside the archive:

```text
power-rangers-skills.zip
├── same-page/
│   └── SKILL.md
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
cp -R same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.claude/skills/
```

Project install:

```sh
mkdir -p .claude/skills
cp -R same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner .claude/skills/
```

Restart Claude Code, then ask:

```text
What Skills are available?
```

### Codex

Install in your Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.codex/skills/
```

Restart Codex so it reloads available skills. If your Codex client uses a repo-local skill directory, copy the skill folders there instead.

## ChatGPT.com Fallback

ChatGPT.com does not install `SKILL.md` folders as native Agent Skills in the same way. Use one of these instead:

- Custom Instructions
- Project Instructions
- Custom GPT instructions

Compact instruction:

```text
Before implementation, orchestrate product strategy, requirements, architecture, risk review, and build planning. Do not write code until the idea is concrete enough to build without guessing at fundamentals.
```

## Testing

Same Page trigger test:

```text
I want to build an app for managing invoices. Help me figure out the plan.
```

Expected behavior: clarification and alignment before implementation.

Specialist trigger test:

```text
Is my invoice app idea worth building for freelance designers?
```

Expected behavior: product strategy analysis before requirements or code.

## Notes

Skills are instruction packages, not system-level rules. They activate when the agent selects them based on the `description`, and they remain lower priority than system/developer instructions.
