---
layout: post
title: "Telling an agent what to do is not a control"
date: 2026-11-14 16:00:00 +0800
categories: [governance, agentic-ai]
tags: [ai-governance, imda, csa, aiverify, chippie, build-in-public]
excerpt: "Singapore's 2026 agentic guidance, what I have actually shipped on a self-hosted assistant, and what I will not claim."
published: false
---

Singapore spent this year turning "agentic AI" from a slide into a set of documents. IMDA updated the Model AI Governance Framework for Agentic AI in May and June. CSA published an addendum on securing agents in June, with a coding assistant as one of the worked examples. In October, IMDA issued a starter kit for testing agentic systems, and the AI Verify Foundation named the first five firms accredited to test generative AI for specific risks.

The ministerial line is still voluntary and case by case. The sentence I keep is from 6 October 2026: we cannot rely on simply telling agents what to do.

That matches what I have shipped on Chippie, my self-hosted assistant, and what I have deliberately left out.

## What I can point at

Chippie asks for confirmation before it saves a skill or a memory change. There is a pause switch. There is an append-only session audit. Since September, a live-chat injection gate and a spend budget sit on the same path.

The coding-agent workflow that builds the repository is a separate layer. It uses role split, review, and permission denies. It does not pretend to be the runtime that talks to me on Telegram and the web.

On 14 November 2026 the product also says, on the login screen and in Telegram help, that the person is talking to an agent, and that a new skill or memory change waits for confirmation. Staged confirm, skip, and "decide later" decisions are written to the session audit with how long the review took. A fast approval is recorded. It is not blocked. A log of a fast click is not proof that the person read the change.

## What I will not imply

I have not commissioned an accredited third-party test. I do not have an AI Verify certificate. Nothing in this stack is an IMDA, CSA, NIST, or EU AI Act compliance claim.

AI Verify remains an assurance toolkit. The October starter kit is testing guidance: name the risks, test the whole trajectory and the tool calls, read the logs, then watch and re-test. The first accredited testers are AIDX Tech, Knovel Engineering, PwC Singapore, Resaro, and Vulcan. Accreditation covers the methods and risk areas a firm demonstrated. It does not mean a system they test is safe. FAIRS, the sector task force on AI-enabled cyber threats, expects a practical report in the first half of 2027. That report is not a test I can pass.

The EU transparency rules have applied since 2 August 2026. High-risk Annex III obligations are later, from 2 December 2027. Chippie is a personal deployment. The part worth copying is the same disclosure Singapore already asked for in May: say it is an agent, and say what it can reach.

NIST's stable documents are still the AI Risk Management Framework 1.0 and the July 2024 Generative AI Profile. The 2026 Cyber AI Profile and the critical-infrastructure profile are drafts.

## What the news is, and is not

[CNA reported on 10 November](https://www.channelnewsasia.com/singapore/sph-media-cyberattack-data-breach-6538681) that SPH Media detected cyberattacks from 4 to 8 November. About 9 percent of the customer database was involved, mostly email, name, mailing address, and phone. The company said payment data and account access were not exposed. CNA said SPH cannot confirm the attacks were AI-enabled while investigations continue; [SPH's own statement](https://www.sph.com.sg/media-centre/media-releases/media-statement-sph-cybersecurity-incident/) does not claim AI. Other outlets the same day said SPH suspects AI-enabled attacks on preliminary investigation. I am not upgrading that to a confirmed finding. The same CNA report mentioned other personal-data incidents that week, including M1, Doctor Anywhere, and Singapore Airlines booking records via Amadeus. I have not re-investigated those. Chippie was not part of them.

On 7 October, Minister Josephine Teo said no Singapore government agency had received a report of a cyberattack involving an unsupervised AI agent. The question referred to a reported Australian case. Safeguards for higher-risk use remain under study. CSA, GovTech, and IMDA also issued a joint advisory on 6 November on the safe use of personal AI agents. That consumer note says not to rely solely on chat instructions to limit what an agent can do.

Reuters and others reported that Nvidia's chief executive resigned on 12 November amid a reported personal relationship and questions about chip exports to China; follow-on coverage said US lawmakers were expanding oversight. I am not treating those allegations as findings. The governance point that survives either outcome is the one the framework already names: third parties, concentrated control, and what you re-open when the control environment changes.

## The control that matters first

If you run a personal agent on your own machine, the first control is structural. Do not register the tool. Do not save the memory until a person confirms. Say, in the product, that it is an agent and what it can see.

A prompt that says "do not do that" is a backstop. It is not the control.

## Sources

- [IMDA Model AI Governance Framework for Agentic AI v1.5](https://www.imda.gov.sg/assets/63438074-73f6-4dcc-a281-030f42642cf4.pdf) (20 May 2026, updated 5 June 2026)
- [CSA addendum on securing agentic AI](https://www.csa.gov.sg/resources/publications/addendum-on-securing-ai-systems/) (17 June 2026)
- [Starter kit for testing agentic systems](https://www.imda.gov.sg/assets/603572eb-724a-46cf-ac12-14fe38e1558c.pdf) (October 2026)
- [MDDI, 6 May 2026](https://www.mddi.gov.sg/newsroom/mddi-s-response-to-pq-on-ensuring-meaningful-human-accountability-for-public-facing-autonomous-ai-agents-and-pathways-to-mandatory-governance-in-high-risk-sectors/)
- [MDDI, 7 July 2026](https://www.mddi.gov.sg/newsroom/mddi-s-response-to-pq-on-key-risk-thresholds-to-regulate-high-risk-ai-deployments-and-implementing-mandatory-human-oversight-for-fully-automated-decisions-materially-affecting-individuals/)
- [Hansard, 6 October 2026](https://openhansard.sg/reports/written-answer-na-25101)
- [EU AI Act implementation timeline](https://ai-act-service-desk.ec.europa.eu/en/ai-act/eu-ai-act-implementation-timeline)
- Earlier notes: [Your AI Second Brain Has No Governance Layer](https://www.linkedin.com/pulse/your-ai-second-brain-has-governance-layer-heres-how-fix-chew-1zofc) and [From Design Spec to Runtime](https://www.linkedin.com/pulse/from-design-spec-runtime-auditing-my-own-ai-governance-ming-yong-chew-klbhc/)

<!-- Promote notes (not rendered): move this file to _posts/, drop published:false, then paste Substack/LinkedIn/X from Chippie repo docs/agent-knowledge/pending/social-drafts/2026-11-15-structural-controls-pack.md. Add Substack cross-link after that post goes live. -->

<!--
LinkedIn feed paste. Not part of the rendered page if this HTML comment survives promotion.
Delete this comment before moving the file to _posts if you do not want it in the source.

Singapore spent this year turning "agentic AI" from a slide into a set of documents: a May/June update of IMDA's Model AI Governance Framework, CSA's June addendum on securing agents, and an October testing starter kit, plus the first five firms accredited to test generative AI for specific risks. The ministerial line is still voluntary. The sentence I keep is from October: we cannot rely on simply telling agents what to do.

That matches what I have shipped on Chippie, and what I have left out. Confirm before a skill or memory write, a pause switch, an append-only session audit, and since September a live-chat injection gate and a spend budget. The coding workflow is a separate layer. I am not claiming an AI Verify certificate or IMDA or CSA compliance.

The news this month is why the distinction matters. SPH Media reported cyberattacks detected 4–8 November and said it cannot confirm they were AI-enabled. Nvidia's chief executive was reported to have resigned while export-control questions are investigated. I am not treating those allegations as findings.

If you run a personal agent, the first control is structural. Do not give it the tool. Do not save the memory until a person confirms. Say, in the product, that it is an agent and what it can see.

Full note (draft, not live until this file moves to _posts): https://github.com/jensonchew/jensonchew.github.io/blob/main/_drafts/2026-11-14-structural-controls-for-a-personal-agent.md

#AIGovernance #AgenticAI #BuildInPublic
-->
