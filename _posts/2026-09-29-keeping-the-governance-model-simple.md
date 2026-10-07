---
layout: post
title: "Keeping the governance model simple"
date: 2026-09-29 09:00:00 +0800
categories: [open-source, agents, governance]
tags: [opencode, cursor, zed, ai-engineering, governance]
excerpt: "Why I kept the agentic governance template to two charters, and how I decide when a new charter is actually worth it."
---

*A small governance model works better than a clever one. The goal is to make boundaries obvious, not multiply labels.*

I’ve been tightening an agentic development governance template I use for structured AI-assisted work, and the biggest lesson so far is simple: **keep the model small unless there is a real reason to expand it**.

The template now stays with two charters:

- **Development**
- **Delivery**

That split has been enough to cover the work that actually matters:

- context and design
- implementation
- review
- CI/CD
- platform and delivery concerns

The main reason I like this split is that it follows the shape of the work, not the shape of a template diagram. It is easy to explain, easy to review, and easy to keep current.

## What changed

I improved a few parts of the template while keeping the structure simple:

- the framework review path is now easier to find
- the reviewer role points directly to the framework PR review checklist
- the framework PR checklist now asks a couple of more concrete questions
- CI runners are pinned so the workflow is more stable and less noisy
- I added contributor guidance for when a third or fourth charter would actually make sense

The last one matters more than it sounds like it does.

## When a new charter is worth it

My rule now is straightforward:

- do not add a new charter just because a topic feels important
- first ask whether the work can stay as a role, checklist, skill, or handoff inside Development or Delivery
- only propose a new charter if there is a stable boundary that repeats over time and genuinely needs its own approval model, accountability model, or operating cadence

That means most things do **not** need a new charter:

- review
- documentation
- architecture guidance
- platform checks
- security review

Those are usually better handled as roles, skills, or checklists inside the existing model.

I also added a short decision checklist in the contributor guide to make that judgement easier:

- Is there a stable boundary that repeats over time?
- Does the work need different approval authority?
- Does it have a different risk or accountability model?
- Does it create repeated handoffs that the current two-charter split cannot hold?
- Does it need a distinct output format or operating cadence?

If the answer to most of those is no, keep the work inside the existing charters.

## Why I prefer that

Every new charter adds structure, but it also adds handoffs and more chances for confusion. Governance should reduce ambiguity, not create new jargon for its own sake.

For me, the right balance is:

- enough structure to be reliable
- not so much structure that people stop using it

That is the main design principle I keep coming back to. The smallest structure that still keeps the work safe, reviewable, and easy to understand is usually the one worth keeping.

## Repo link

If you want to inspect the template itself, the repo is here:

https://github.com/jensonchew/agentic-dev-governance-template

## Related reads

- [Substack version](https://jensonchew.substack.com)
- [LinkedIn version](https://www.linkedin.com/in/jensonchew/recent-activity/articles/)

I’ll keep refining the template over time, but the direction is clear: use the smallest structure that still makes the work understandable and safe.
