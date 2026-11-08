# Harness Audit

A portable, English-language skill for reviewing AI skills, agent instructions, or an entire AI harness: the instructions, context sources, tools, and execution rules surrounding an agent.

It helps you assess whether your setup makes AI-assisted work understandable, supplies relevant context, verifies outcomes with evidence, learns from confirmed problems, and keeps people responsible for consequential decisions. It works across IT roles and projects without requiring a particular toolchain.

## What an audit produces

A bounded assessment with material findings, supporting evidence, consequences, focused recommendations, and ways to validate them. The auditor checks inherited rules and existing authorizations, distinguishes declared configuration from observed behavior, and reports gaps in its own coverage.

The same principles apply to the auditor. Before reporting, it must challenge its findings, check its recommendations against access and state-preservation constraints, and disclose material limitations or deviations.

Review is read-only by default. The skill does not authorize running the reviewed workflows or applying fixes. A report supports your judgment; it does not guarantee correctness or replace technical access controls.

## Installation

These instructions cover local Claude Code and Codex installations on macOS or Linux. You need Git and the relevant agent installed.

### 1. Download the repository

```bash
mkdir -p ~/Projects
git clone https://github.com/Veador/harness-audit-skill.git ~/Projects/harness-audit-skill
```

If you already have this repository, use that checkout instead. The commands below assume it is at `~/Projects/harness-audit-skill`.

### 2. Install for your agent

Choose either or both. Each option copies the two skill files into a user-level skills directory.

#### Claude Code

```bash
mkdir -p ~/.claude/skills/harness-audit/references
cp ~/Projects/harness-audit-skill/SKILL.md ~/.claude/skills/harness-audit/
cp ~/Projects/harness-audit-skill/references/principles.md ~/.claude/skills/harness-audit/references/
```

Invoke it in Claude Code:

```text
/harness-audit Review my local skills and agent instructions. First establish the permitted sources and exclusions. Report findings without changing files or running workflows.
```

For installation in one project, use `.claude/skills/harness-audit/` inside that project instead of the user-level directory. See the [official Claude Code skills documentation](https://code.claude.com/docs/en/skills).

#### Codex

```bash
mkdir -p ~/.agents/skills/harness-audit/references
cp ~/Projects/harness-audit-skill/SKILL.md ~/.agents/skills/harness-audit/
cp ~/Projects/harness-audit-skill/references/principles.md ~/.agents/skills/harness-audit/references/
```

Invoke it in Codex:

```text
$harness-audit Review my local skills and agent instructions. First establish the permitted sources and exclusions. Report findings without changing files or running workflows.
```

For installation in one project, use `.agents/skills/harness-audit/` inside that project instead of the user-level directory. Use `/skills` to check discovery in Codex CLI or its IDE extension. If the new skill does not appear, restart Codex. See the [official OpenAI skills documentation](https://learn.chatgpt.com/docs/build-skills).

### Updates

Pull changes into your checkout, then repeat the copy commands for each installed agent:

```bash
git -C ~/Projects/harness-audit-skill pull --ff-only
```

Copying replaces the installed files. Preserve any local customizations before updating.

## Skill files

- [SKILL.md](SKILL.md): audit procedure, access boundaries, self-check, and report requirements.
- [references/principles.md](references/principles.md): the principles used to assess both the target and the audit itself.
