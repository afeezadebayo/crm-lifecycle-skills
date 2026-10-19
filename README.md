# CRM & Lifecycle Marketing — SKILL.md files for AI agents

[![13 skills](https://img.shields.io/badge/skills-13-0b7285)](#whats-inside)
[![Format: Agent Skills](https://img.shields.io/badge/format-SKILL.md-5f3dc4)](https://agentskills.io/specification)
[![Works with Claude Code & Codex](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Codex%20%7C%20Claude.ai-1c7ed6)](#install)
[![Licence: CC BY 4.0](https://img.shields.io/badge/licence-CC%20BY%204.0-2b8a3e)](https://creativecommons.org/licenses/by/4.0/)

Free, ready-to-run **CRM & lifecycle marketing** skills for **Claude, Claude Code, OpenAI Codex** and any agent that
reads the [Agent Skills](https://agentskills.io/specification) format. Move people from sign-up to loyal customer and
back again when they drift: journey mapping, segmentation, lead scoring, onboarding, retention, win-back,
deliverability and reporting, for HubSpot, Salesforce, Klaviyo, Braze, Customer.io and similar tools. Each skill is a
single `SKILL.md`: a senior practitioner's workflow — when to use it, the inputs to ask for, a numbered process,
decision rules, an output template and sources — loaded only when a task needs it.

Part of the [Marketing Skills library](https://github.com/afeezadebayo/marketing-skills) by
[Afeez Adebayo](https://afeezadebayo.com) · [Browse online](https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/)

## Install

Each skill is its own folder with a `SKILL.md`, so you can drop any folder straight into an agent.

**Claude Code**
```bash
git clone https://github.com/afeezadebayo/crm-lifecycle-skills.git
cp -r crm-lifecycle-skills/onboarding-activation ~/.claude/skills/        # all projects
# or  .claude/skills/   inside one project
```

**OpenAI Codex**
```bash
cp -r crm-lifecycle-skills/onboarding-activation ~/.agents/skills/         # all repos
```

**Claude.ai / Desktop** — zip a skill folder, then **Settings → Capabilities → Skills → Upload skill**
(code execution must be enabled). To bulk-load the whole category into a Claude Project, custom GPT or
knowledge base, grab the single-folder `.zip` from the
[library page](https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/).

Then start a new session and ask your agent which skills it can use.

## What's inside

| Skill | What it does |
|---|---|
| [`lifecycle-marketing-audit`](lifecycle-marketing-audit/SKILL.md) | Audit a whole CRM and lifecycle programme across eight layers with a scored 90-day plan. The entry point. |
| [`customer-journey-mapping`](customer-journey-mapping/SKILL.md) | Build a lifecycle journey map from behaviour data: stages, the value moment, stalls and a blueprint. |
| [`lifecycle-segmentation`](lifecycle-segmentation/SKILL.md) | Build segments that drive action: engagement tiers, RFM, intent, an action matrix and sunset policy. |
| [`crm-data-hygiene`](crm-data-hygiene/SKILL.md) | Audit and fix CRM data: completeness, consent records, deduplication and source fixes. |
| [`lead-scoring-routing`](lead-scoring-routing/SKILL.md) | Build B2B lead scoring and routing from closed-won data, with fit/intent matrices and speed-to-lead. |
| [`onboarding-activation`](onboarding-activation/SKILL.md) | Design onboarding that gets new customers to first value fast, with stall branches and holdouts. |
| [`retention-churn-prevention`](retention-churn-prevention/SKILL.md) | Reduce churn before it happens: health scores, dunning, matched interventions and fair cancellation flows. |
| [`win-back-reactivation`](win-back-reactivation/SKILL.md) | Win back lapsed customers without hurting deliverability or margin, measured against a holdout. |
| [`email-deliverability`](email-deliverability/SKILL.md) | Get email into the inbox under 2026 Google/Yahoo/Microsoft rules: SPF, DKIM, DMARC, complaints, warming. |
| [`lifecycle-email-copy-design`](lifecycle-email-copy-design/SKILL.md) | Write and review lifecycle emails that get one clear action, mobile-first and accessible. |
| [`sms-whatsapp-lifecycle`](sms-whatsapp-lifecycle/SKILL.md) | Use SMS and WhatsApp for the moments that matter, with consent, compliance and cost control. |
| [`lifecycle-experimentation`](lifecycle-experimentation/SKILL.md) | Measure what lifecycle marketing really adds: holdouts, A/B tests, sample size and honest reporting. |
| [`lifecycle-reporting-attribution`](lifecycle-reporting-attribution/SKILL.md) | Build reporting leadership can trust: a metric dictionary, incrementality and cohort retention views. |

## How these skills work

Agents use *progressive disclosure*: they read each skill's `name` and `description` (~100 tokens) at the start
of a session and load the full `SKILL.md` only when your request matches — so you can install many without
filling the context window.

## Author & licence

By [**Afeez Adebayo**](https://afeezadebayo.com) — Marketing, SEO & Growth (SEO & Organic Growth at Grey, YC W22).
[LinkedIn](https://www.linkedin.com/in/afeez-adebayo/) · [X](https://x.com/za_icon) · [Newsletter](https://afeezadebayo.com/newsletter/)

Released under [**CC BY 4.0**](https://creativecommons.org/licenses/by/4.0/) — use, share and adapt, including
commercially, with credit to Afeez Adebayo and a link to the source page in each file.

<sub>Keywords: CRM skills, lifecycle marketing, SKILL.md, Agent Skills, Claude skills, Claude Code skills, Codex
skills, AI agent skills, customer journey mapping, segmentation, lead scoring, onboarding, retention, churn
prevention, win-back, email deliverability, SMS, WhatsApp, marketing automation, HubSpot, Salesforce, Klaviyo,
Braze, Customer.io.</sub>
