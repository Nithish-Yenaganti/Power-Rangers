# PowerRangers Skills

This repository contains Claude/Codex-compatible Agent Skills. Each skill is a folder with a `SKILL.md` file containing YAML frontmatter and Markdown instructions.

## Skills

```text
anti-yap-ranger/
└── SKILL.md

same-page/
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

`same-page` is for clarification-first planning before implementation.

Use it when the user has an idea but the requirements are not clear enough to build yet.

It helps align on:

- problem and target user
- desired behavior
- scope and non-goals
- stack and runtime
- architecture and system boundaries
- risks and unknowns
- execution plan

This skill intentionally slows down implementation at the start so the agent does not build the wrong thing.

## Compatibility

Both skills follow the shared Claude/Codex-friendly structure:

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
cp -R anti-yap-ranger same-page ~/.claude/skills/
```

Project install:

```sh
mkdir -p .claude/skills
cp -R anti-yap-ranger same-page .claude/skills/
```

Restart Claude Code, then ask:

```text
What Skills are available?
```

### Codex

Install in your Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R anti-yap-ranger same-page ~/.codex/skills/
```

Restart Codex so it reloads available skills. If your Codex client uses a repo-local skill directory, copy both folders there instead.

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
Before implementation, align on requirements, scope, constraints, stack, architecture, risks, and execution plan. Do not write code until the idea is concrete enough to build without guessing at fundamentals.
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

## Notes

Skills are instruction packages, not system-level rules. They activate when the agent selects them based on the `description`, and they remain lower priority than system/developer instructions.
