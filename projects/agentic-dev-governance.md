---
layout: page
title: Agentic Dev Governance Template
permalink: /projects/agentic-dev-governance/
description: OpenCode starter for orchestrator-led development and delivery workflows.
repo: https://github.com/jensonchew/agentic-dev-governance-template
tags:
  - open-source
  - opencode
  - agents
---

# Agentic Dev Governance Template

Stack-agnostic **OpenCode governance template** for orchestrator-led development and delivery workflows.

**[Use this template on GitHub](https://github.com/jensonchew/agentic-dev-governance-template/generate)** · [Repository](https://github.com/jensonchew/agentic-dev-governance-template)

## What you get

- Multi-agent governance in `AGENTS.md` with development and delivery charters
- **Development flow:** context mapping → design analysis → spec writing → implementation → review
- **Delivery flow:** pipeline review, platform evaluation, security, observability
- Spec-before-implement for non-trivial changes
- Reusable skills in `.agents/skills/` and OpenCode skills in `.opencode/skills/`
- `/setup` command to generate stack-specific rules for your repo
- Just-in-time context loading — agents load only what the current task requires

## Who it's for

Teams or solo developers using **Cursor, OpenCode, or Zed** who want phased agent workflows with role separation, without building governance from scratch.

## What it's not

This template covers **how to build software with agents**. It is not a personal AI assistant, Telegram bot, or production runtime governance stack. I use a similar pattern in a private assistant monorepo; this repo is the portable, forkable extract.

## Quick start

1. Click **Use this template** on GitHub.
2. Open the repo in OpenCode and run `/setup` with your stack description.
3. Review generated `REPOSITORY-CONTEXT.md` and `.agents/instructions-stack.md`.
4. Use the development orchestrator for non-trivial work.

## License

MIT — see [LICENSE](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/LICENSE). Vendored OpenCode skills are noted in [NOTICE](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/NOTICE).
