---
layout: page
title: Agentic Dev Governance Template
permalink: /projects/agentic-dev-governance/
description: IDE-agnostic governance template for orchestrator-led development and delivery workflows.
repo: https://github.com/jensonchew/agentic-dev-governance-template
tags:
  - open-source
  - agents
  - governance
  - cursor
  - zed
---

# Agentic Dev Governance Template

**IDE-agnostic** governance template for orchestrator-led development and delivery — works with **OpenCode**, **Cursor**, **Zed**, and **VS Code**.

**[Use this template on GitHub](https://github.com/jensonchew/agentic-dev-governance-template/generate)** · [Repository](https://github.com/jensonchew/agentic-dev-governance-template) · [IDE adapters](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/docs/IDE_ADAPTERS.md) · [Zed quickstart](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/docs/examples/zed-quickstart.md)

## What you get

- Multi-agent governance in `AGENTS.md` with development and delivery charters
- **Portable role packs** in `.agents/roles/` — same files across IDEs
- Development flow: context mapping → design analysis → spec writing → implementation → review
- Delivery flow: pipeline review, platform evaluation, security, observability
- Spec-before-implement for non-trivial changes
- Reusable skills in `.agents/skills/` (agent-agnostic)
- OpenCode runtime wiring in `opencode.json` + `.opencode/skills/` (optional)
- `/setup` in OpenCode to generate stack-specific rules

## IDE support

| IDE | How |
|-----|-----|
| **OpenCode** | Full orchestrator wiring via `opencode.json` + `/setup` |
| **Cursor** | `AGENTS.md` + thin `.cursor/rules/` pointers to `.agents/` |
| **Zed** | `AGENTS.md` auto-loaded; [zed quickstart](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/docs/examples/zed-quickstart.md) |
| **VS Code** | Workspace instructions → `AGENTS.md` + role files |

## Who it's for

Teams or solo developers using any major AI-enabled editor who want phased agent workflows with role separation, without building governance from scratch.

## What it's not

This template covers **how to build software with agents**. It is not a personal AI assistant, Telegram bot, or production runtime governance stack. OpenCode files are convenience adapters — the governance model is not locked to one IDE.

## Quick start

1. Click **Use this template** on GitHub.
2. Read `AGENTS.md` and `docs/IDE_ADAPTERS.md` for your editor.
3. Customize `REPOSITORY-CONTEXT.md` (or run `/setup` in OpenCode).
4. Use phased workflows from `.agents/roles/` for non-trivial work.

## License

MIT — see [LICENSE](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/LICENSE). Vendored OpenCode skills are noted in [NOTICE](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/NOTICE).
