# PowerRangers Skills

This repository contains Claude/Codex-compatible Agent Skills. Each skill is a folder with a `SKILL.md` file containing YAML frontmatter and Markdown instructions.

## Skills

```text
anti-yap-ranger/
└── SKILL.md

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

## Anti-Yap Ranger

`anti-yap-ranger` is for concise, high-signal responses.

Use it when the task benefits from:

- terse summaries
- answer-first output
- token-efficient coding loops
- concise debugging updates
- direct comparisons
- RAG/search synthesis

It does not mean "short at all costs." The skill prioritizes:

1. Correctness and verified facts
2. User actionability
3. Professional clarity
4. Necessary context, risks, and next steps
5. Brevity

The goal is useful work per token.

## Same Page

`same-page` is the orchestrator for idea-to-product alignment before implementation.

Use it when the user has an idea but the strategy, requirements, architecture, risks, or plan are not clear enough to build yet.

It coordinates these specialist lenses:

- `product-strategist` - is this idea worth building?
- `requirements-analyst` - what exactly are we building?
- `architecture-advisor` - how should it be built?
- `risk-reviewer` - what can go wrong?
- `build-planner` - how do we execute?

This setup intentionally slows down implementation at the start so the agent does not build the wrong thing, change route mid-build, or damage the codebase with unstable requirements.

## Specialist Skills

`product-strategist` checks the customer, pain, alternatives, differentiation, value capture, and success metrics.

`requirements-analyst` turns the idea into v1 scope, user flows, non-goals, edge cases, and acceptance criteria.

`architecture-advisor` recommends stack, runtime, data model, integrations, system boundaries, and maintainability tradeoffs.

`risk-reviewer` identifies assumptions, failure modes, security/privacy issues, adoption risk, maintainability risk, and route-change risk.

`build-planner` creates the phased implementation route after alignment is complete.

## Compatibility

All skills follow the shared Claude/Codex-friendly structure:

- folder name matches `name`
- file is named `SKILL.md`
- YAML frontmatter includes `name` and `description`
- names use lowercase letters and hyphens
- descriptions are under 200 characters for Claude.ai upload compatibility
- body uses plain Markdown
- instructions and examples are included

## Install

### Claude.ai

Zip the skill folders so they are inside the archive:

```text
power-rangers-skills.zip
├── anti-yap-ranger/
│   └── SKILL.md
├── product-strategist/
│   └── SKILL.md
├── requirements-analyst/
│   └── SKILL.md
├── architecture-advisor/
│   └── SKILL.md
├── risk-reviewer/
│   └── SKILL.md
├── build-planner/
│   └── SKILL.md
└── same-page/
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
cp -R anti-yap-ranger same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.claude/skills/
```

Project install:

```sh
mkdir -p .claude/skills
cp -R anti-yap-ranger same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner .claude/skills/
```

Restart Claude Code, then ask:

```text
What Skills are available?
```

### Codex

Install in your Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R anti-yap-ranger same-page product-strategist requirements-analyst architecture-advisor risk-reviewer build-planner ~/.codex/skills/
```

Restart Codex so it reloads available skills. If your Codex client uses a repo-local skill directory, copy the skill folders there instead.

## ChatGPT.com Fallback

ChatGPT.com does not install `SKILL.md` folders as native Agent Skills in the same way. Use one of these instead:

- Custom Instructions
- Project Instructions
- Custom GPT instructions

Compact Anti-Yap instruction:

```text
Be concise and high-density. Skip filler, preambles, prompt mirroring, and unnecessary caveats. Spend tokens on accuracy, verification, and actionable output. Keep reasoning internal. Ask only when a wrong assumption would be costly. Put final results before explanation.
```

Compact Same Page instruction:

```text
Before implementation, orchestrate product strategy, requirements, architecture, risk review, and build planning. Do not write code until the idea is concrete enough to build without guessing at fundamentals.
```

## Testing

Anti-Yap Ranger trigger test:

```text
Compare REST and GraphQL. Keep it practical.
```

Expected behavior: compact answer, likely bullets or a table, no filler intro.

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
