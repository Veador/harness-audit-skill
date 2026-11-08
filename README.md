# Harness Audit

A portable, English-language skill for reviewing AI skills, agent instructions, or an entire AI harness: the instructions, context sources, tools, and execution rules surrounding an agent.

It helps you assess whether your setup makes AI-assisted work understandable, supplies relevant context, verifies outcomes with evidence, learns from confirmed problems, and keeps people responsible for consequential decisions. It works across IT roles and projects without requiring a particular toolchain.

## What an audit produces

A bounded assessment with material findings, supporting evidence, consequences, focused recommendations, and ways to validate them. The auditor checks inherited rules and existing authorizations, distinguishes declared configuration from observed behavior, and reports gaps in its own coverage.

The same principles apply to the auditor. Before reporting, it must challenge its findings, check its recommendations against access and state-preservation constraints, and disclose material limitations or deviations.

Review is read-only by default. The skill does not authorize running the reviewed workflows or applying fixes. A report supports your judgment; it does not guarantee correctness or replace technical access controls.

## Installation

1. [Download the ZIP archive](https://github.com/Veador/harness-audit-skill/archive/refs/heads/main.zip).
2. Give the archive to your AI agent and ask it to install the skill from it.

## Skill files

- [SKILL.md](SKILL.md): audit procedure, access boundaries, self-check, and report requirements.
- [references/principles.md](references/principles.md): the principles used to assess both the target and the audit itself.
