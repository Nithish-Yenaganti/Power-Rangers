# Anti-Yap Ranger

A small Agent Skill for concise, high-density responses and token-efficient agent work.

## Files

```text
anti-yap-ranger/
└── SKILL.md
```

No scripts, references, assets, or extra config files are required.

## Install

### Claude.ai

1. Zip the skill folder so the folder is inside the archive:

   ```text
   anti-yap-ranger.zip
   └── anti-yap-ranger/
       └── SKILL.md
   ```

2. In Claude.ai, open `Customize > Skills`.
3. Upload the zip file.
4. Enable the skill.
5. Test with a prompt like: `Answer concisely using Anti-Yap Ranger style.`

Claude requires the folder name to match the `name` field in `SKILL.md`.

### Claude Code

For a personal install:

```sh
mkdir -p ~/.claude/skills
cp -R anti-yap-ranger ~/.claude/skills/
```

For a project install:

```sh
mkdir -p .claude/skills
cp -R anti-yap-ranger .claude/skills/
```

Then restart Claude Code or ask it:

```text
What Skills are available?
```

### Codex

For this Codex-style skill layout, install it in your Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R anti-yap-ranger ~/.codex/skills/
```

Restart Codex so it reloads available skills. If your Codex client uses a repo-local skill directory, copy `anti-yap-ranger/` there instead.

### ChatGPT.com

ChatGPT.com does not currently install `SKILL.md` folders as native Agent Skills. Use one of these instead:

- **Custom Instructions**: paste the core rules from `anti-yap-ranger/SKILL.md` into `Settings > Personalization > Custom Instructions`.
- **Project Instructions**: create a project and paste the core rules into the project instructions.
- **Custom GPT**: create a GPT, paste the rules into its Instructions, and optionally upload `SKILL.md` as a knowledge file.

Suggested compact ChatGPT instruction:

```text
Use Anti-Yap Ranger style: be concise and high-density. Skip filler, preambles, prompt mirroring, and unnecessary caveats. Spend tokens on accuracy, verification, and actionable output. Keep reasoning internal. Ask only when a wrong assumption would be costly. Put results before explanation.
```

## Share

Publish the repository or attach `anti-yap-ranger.zip`. Users who need Claude.ai should upload the zip. Users of Claude Code or Codex can copy the folder into their local skills directory.
