---
layout: post
title: "Always-on is not unbounded"
date: 2026-10-07 09:00:00 +0800
categories: [agents, governance, privacy]
tags: [always-on-agents, ai-governance, pdpa, imda, ai-engineering]
excerpt: "The guardrails I run on about 10 always-on AI agents (draft-before-send, approval gates, confirmed-delivery logging, revocable connectors) and the gaps I haven't closed yet."
---

*Always-on is fine. Unbounded is not. Here are the controls I run, where they failed, and a free guardrails template.*

I run about 10 always-on AI agents. They triage, research, remind, draft and watch things for me around the clock.

Not one of them can send a message to anyone without me seeing it first.

That's not because I distrust the technology. It's because I've spent the past 13 years doing operational compliance work, including VAPT and Singapore government IM8 controls, procurement and vendor management. That work taught me one thing that carries straight over to agents: **capability is easy to switch on, but accountability isn't.**

This piece covers the controls I actually run, the places where they've failed me, and the gaps I haven't closed yet. It is not a product pitch, and it is not a reference architecture.

## Why this matters now

The "agent that works while you sleep" is no longer a hobbyist setup.

On 29 September 2026 OpenAI introduced dots, always-on agents with Custom Rules that let you "allow specific actions, require approval, or block them" ([OpenAI](https://openai.com/index/introducing-dots/)). That is allow / approve / block, the same three-way split I've been running by hand.

Meanwhile WIRED reported that Meta's Muse builds "a page for every person in the user's life", refreshed hourly, covering family, partners, friends and colleagues ([WIRED](https://www.wired.com/story/muse-creates-detailed-profiles-of-all-your-friends-and-family/)). Meta says it uses "public information and … what you've chosen to share" ([Meta](https://www.meta.com/help/artificial-intelligence/2225571704857152/)). The people on those pages weren't asked.

And Instinct's Trusted Person feature now lets one person's agent coordinate directly with another person's agent, with a separate access level for each connection ([Business Insider](https://www.businessinsider.com/why-couples-are-using-ai-agents-instinct-emotional-labor-2026-9)).

Vendors are converging on the right controls. But a platform toggle is a starting point, not a governance model. Someone still has to decide what goes in each bucket, and that someone is you.

## The controls I run

These are boring on purpose. Boring is what survives 3am.

**1. Draft-before-send for anything outgoing.**
Any email, message, post or reply to someone other than me is a draft until I approve it. A past "yes" covers that one message, never the next one.

**2. Read-only access to finance accounts.**
My agents can see balances and transactions. They can't move money. If an agent ever needs to pay for something, that happens on a device I control, with me pressing the button.

**3. Approval gates on risky actions.**
Deleting, overwriting, merging code, changing account settings, contacting someone new: all of these stop and wait for me. The test is reversibility and blast radius, not how confident the agent sounds.

**4. Never-access lists.**
Some systems are off-limits no matter what the task is. I don't rely on the agent working out that something is sensitive. I write the list down.

**5. Token and credit budgets.**
Always-on means always spending. Each setup has a budget, and I get warned at 50%, 75% and 90% of it, so I know before it runs out rather than after.

**6. A pre-command guard and a 3-retry circuit breaker for coding agents.**
I added both to my own agent setup on 3 Oct 2026. The guard checks a command before it runs. The breaker stops an agent after three failed attempts at the same action, instead of letting it "creatively" work around the failure.

That last one matters more than it sounds like it does. A looping agent doesn't just burn credits. It starts looking for side doors.

## The incident that changed my logging

Here's one that humbled me.

One of my agents reported that it had sent a Telegram alert. It hadn't reached my phone. I only noticed when I checked the chat myself.

Nothing malicious happened. But "reported as done" and "actually done" had quietly drifted apart, and I only found out by accident.

So I added **confirmed-delivery logging**. An action is logged as complete only after it's been confirmed to have succeeded. If it failed or was blocked, the agent has to say so plainly.

My rule now is straightforward: **done means verified, not reported.**

## A connector is a standing door

Trying Instinct showed me something I now watch for carefully: an always-on assistant can keep access to accounts like Google and GitHub after you've moved on.

That's not a dig at Instinct. The grant is yours to remove. Every connector you approve is a standing door until you close it, and that's what concerns me.

So two rules:

- **Revocable, not permanent.** Connect through OAuth or app-specific access you can revoke, never your main password.
- **Reviewed, not forgotten.** Do a regular access review, revoke unused grants, and clear stale sessions. In my IM8 and audit days this was a routine user-access review. It works the same way for agents.

## The infrastructure gap nobody talks about

Most of my agents run on one machine. That means they **share the same browser sessions**.

A login I make for one agent is, in practice, reachable by all of them. Per-agent scopes look great on paper, but the shared session store sits underneath them.

I haven't fully fixed this. For now I've accepted it as a known risk and I'm careful which logins I make on that machine.

Honest limit: this is a solo setup. It illustrates the controls. It isn't a design for an organisation.

## Your agent's memory is a personal-data register

This is the part I think most people underestimate.

An always-on agent's memory isn't only about you. It's about everyone you email, message and meet: people who never signed up for your agent.

I now treat agent memory the way I'd treat any personal-data register:

- **Minimum necessary.** Keep only what a task I asked for actually needs. No profiling of people in my life.
- **Accurate and reviewable.** I should be able to see what it holds and correct it.
- **Retention.** This is my gap. I don't have a purge rule for workspace files yet. What I intend to adopt: keep task notes for 90 days, clear chat and workspace junk weekly, and don't keep third-party personal data longer than the task needs.
- **Location.** Know where the memory lives, which provider and which region, and whether it's used for training.

Singapore's PDPA is a useful lens here, with one caveat. The Act generally doesn't apply to an individual acting in a personal or domestic capacity ([PDPC](https://www.pdpc.gov.sg/overview-of-pdpa/the-legislation/personal-data-protection-act)). My personal agents probably fall outside it. But the organisations running the platforms don't, and the moment an agent touches work data, neither do I.

The obligations still make a good checklist ([PDPC, Data Protection Obligations](https://www.pdpc.gov.sg/data-protection-obligations)):

- **Consent and purpose limitation:** would the people in my agent's memory reasonably expect their details to be used this way?
- **Retention limitation:** stop keeping data once it's no longer needed.
- **Transfer limitation:** most of these services run outside Singapore. Data about Singaporeans may be crossing borders every time an agent syncs.

Not legal advice. A lens, not a ruling.

## How this maps to Singapore's agentic AI framework

IMDA's Model AI Governance Framework for Agentic AI (v1.5, May 2026) organises guidance into four dimensions ([IMDA](https://www.imda.gov.sg/assets/63438074-73f6-4dcc-a281-030f42642cf4.pdf); [Baker McKenzie summary](https://www.bakermckenzie.com/en/insight/publications/2026/06/singapore-imda-updates-model-ai-governance-framework-for-agentic-ai)). My controls map onto them roughly like this:

| IMDA dimension | My controls |
|---|---|
| Assess and bound the risks upfront | Never-access lists, read-only finance access, budgets |
| Make humans meaningfully accountable | Draft-before-send, approval gates |
| Implement technical controls and processes | Pre-command guard, circuit breaker, confirmed-delivery logging |
| Enable end-user responsibility | Revocable connectors, access reviews, memory hygiene |

v1.5 also addresses multi-agent and third-party-agent risks and automation bias (same sources). Both are real. When you approve drafts all day, "approve" can turn into a reflex. Mapped to the framework doesn't mean certified by it.

## What this is NOT

- **Not** a claim that my setup is compliant or audited.
- **Not** a reference architecture for an agency or enterprise.
- **Not** anti-agent. I run them because they're useful.
- **Not** finished. The shared-session and retention gaps are still open.

## Take the guardrails

I've turned all of this into a vendor-neutral starter policy: paste-in agent instructions, an owner checklist, and a starter risk register. It's free. Adapt it, don't adopt it blindly.

**Download: [Always-On AI Agent Guardrails](/assets/downloads/always-on-agent-guardrails.md)**

I'm sitting the IAPP AIGP exam on 31 October, and writing this has been better revision than any flashcard.

Always-on is fine. Unbounded is not.

---

## Related reads

- [Substack version](https://jensonchew.substack.com)
- [LinkedIn version](https://www.linkedin.com/in/jensonchew/recent-activity/articles/)
- [Agentic dev governance template](https://github.com/jensonchew/agentic-dev-governance-template)
