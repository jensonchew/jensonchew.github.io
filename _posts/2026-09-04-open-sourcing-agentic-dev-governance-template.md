---
layout: post
title: "Open-sourcing my agentic dev governance template (not my personal AI assistant)"
date: 2026-09-04 14:00:00 +0800
categories: [open-source, agents, governance]
tags: [opencode, cursor, zed, ai-engineering]
excerpt: "IDE-agnostic dev/delivery governance you can fork—separate from runtime governance on a private assistant."
---

*A portable, IDE-agnostic harness for spec-before-implement and role-separated agent workflows (OpenCode, Cursor, Zed, VS Code)—separate from runtime governance on a self-hosted assistant.*

In May and July I wrote about **runtime governance** for personal AI assistants: session audit, kill switches, ingest gates. That work lives in production code on a **private** assistant stack—not in [this public template](https://github.com/jensonchew/agentic-dev-governance-template).

Today I'm open-sourcing a different layer: the **development governance template** I use with agents in **OpenCode, Cursor, and Zed** (same `.agents/` role packs; IDE-specific adapter only).

## Two layers (don't conflate them)

| Layer | What it is | Where |
|-------|------------|--------|
| **Runtime governance** | Audit logs, circuit breakers, injection gates on a running assistant | Private product code + [prior Pulse articles](https://www.linkedin.com/in/ming-yong-chew/recent-activity/articles/) |
| **Dev governance** | Orchestrator-led dev/delivery, spec-before-implement, role separation | **[Public template](https://github.com/jensonchew/agentic-dev-governance-template)** |

## What the template gives you

- Development and delivery **charters** with orchestrators that delegate (not improvise in one thread)
- **Context mapper → spec writer → implementer → reviewer** phased workflow
- `/setup` in OpenCode to generate stack-specific rules (or edit `REPOSITORY-CONTEXT.md` manually in other IDEs)
- Just-in-time context loading — agents load policy only when the task needs it
- **IDE adapters** for Cursor, Zed, VS Code — see [IDE_ADAPTERS.md](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/docs/IDE_ADAPTERS.md)
- Reusable skills (TDD, zoom-out, grill-with-docs, handoff)

## What it is NOT

- Not a Telegram bot or personal assistant product
- Not runtime session governance or compliance certification
- Not locked to OpenCode — `opencode.json` is optional runtime wiring

## Who it's for

Solo devs or teams adopting multi-agent IDE workflows who want structure without reinventing governance from scratch.

## Quick start

1. [**Use this template**](https://github.com/jensonchew/agentic-dev-governance-template/generate) on GitHub
2. Read `AGENTS.md` + [IDE adapters](https://github.com/jensonchew/agentic-dev-governance-template/blob/master/docs/IDE_ADAPTERS.md) for your editor (OpenCode: run `/setup`)
3. Use the development orchestrator for non-trivial work

**Project overview:** [jensonchew.github.io/projects/agentic-dev-governance/]({{ '/projects/agentic-dev-governance/' | relative_url }})

If you already read my runtime governance pieces, treat this as the **engineering harness** companion—the part you can fork today without inheriting my operator setup.

---

*Also on [LinkedIn](https://www.linkedin.com/pulse/open-sourcing-my-agentic-dev-governance-template-personal-chew-v2llf/).*

*Coming on Substack: **Engineering Trust: The Governance Pillars of Agentic Workflows in the Public Sector** — the policy and assurance layer behind this harness.*
