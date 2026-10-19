---
name: lifecycle-marketing-audit
description: "Audit a whole CRM and lifecycle marketing programme across eight layers (data and events, consent, segmentation, journeys and flows, channels, deliverability, content and offers, measurement) for Klaviyo, Braze, HubSpot, Customer.io, Iterable or Salesforce, map lifecycle stages from events, find coverage gaps and overlapping flows, separate attributed from incremental revenue and produce a scored 90-day plan. Use whenever someone asks for a lifecycle audit, CRM audit, email marketing audit, retention marketing review, flow audit, or wants to know what their email, SMS and lifecycle programme is really worth."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-marketing-audit/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Lifecycle Marketing Audit

Lifecycle marketing is everything a business does to move people from first sign-up to active, loyal, paying customer, and back again when they drift. Most programmes grow by accretion: a welcome email here, a cart reminder there, a newsletter nobody owns. The result is overlapping messages, missing stages, unreliable data and reports that credit email with revenue it didn't cause.

This skill audits the whole system in one pass: data, segments, journeys, channels, deliverability, content, experimentation and measurement. It scores each layer, finds the gaps that cost the most revenue, and hands each finding to the specialist skill that fixes it. It is the entry point for the CRM and Lifecycle set.

## Operating principles
1. **Start from the customer journey, not the tool.** Map the stages people actually go through, then check what the programme does at each one.
2. **Incrementality over attribution.** A flow that "drove" revenue may only have touched people who would have bought anyway. Ask what holdouts show.
3. **Deliverability is a gate.** Messages that land in spam or are rejected make every other improvement worthless.
4. **Fewer, better messages.** Frequency and overlap are a common cause of unsubscribes and complaints.
5. **Consent and preferences are part of the product.** Treat legal requirements as the floor and customer expectations as the standard.

## When to use, and when not to
Use it when inheriting a CRM or lifecycle programme, before a platform migration (for example Mailchimp to Klaviyo, or HubSpot to Braze), when retention or repeat purchase is falling, when email revenue looks too good to be true, or when leadership asks what lifecycle actually contributes.

Don't use it to write a single email (`lifecycle-email-copy-design`), to fix a deliverability incident in progress (`email-deliverability`) or to design one journey in depth (the programme skills: `onboarding-activation`, `retention-churn-prevention`, `win-back-reactivation`).

## Inputs to ask for, in one message
1. Business model: B2C or B2B, subscription, e-commerce, marketplace or SaaS; average order or contract value; purchase frequency.
2. Platforms in use: CRM (HubSpot, Salesforce), messaging (Klaviyo, Braze, Customer.io, Iterable, Mailchimp), SMS and WhatsApp providers, CDP or warehouse.
3. A list of live flows and campaigns with triggers, audiences, sends and results for the last 90 days.
4. Deliverability data: Google Postmaster Tools, Microsoft SNDS, bounce and complaint rates, authentication records.
5. Customer data: lifecycle stage definitions, key events tracked, consent fields, list size and growth.
6. Revenue and retention metrics: repeat rate, churn, cohort retention curves, and how email and SMS revenue is attributed.
7. Any holdout or incrementality tests run in the past.

## The eight layers
| Layer | What to check | Typical high-impact finding |
|---|---|---|
| 1. Data and events | Key events tracked, identity resolution, data freshness, field hygiene | Purchase or activation events missing, so flows trigger on the wrong behaviour |
| 2. Consent and preferences | Opt-in records, preference centre, channel-specific consent, suppression | SMS sent without recorded consent; no way to reduce frequency |
| 3. Segmentation and stages | Stage definitions, RFM or engagement tiers, exclusions | "Active" defined by opens, which Apple Mail Privacy Protection inflates |
| 4. Journeys and flows | Coverage of each stage, triggers, exits, overlap and priority rules | No onboarding beyond one welcome email; customers in four flows at once |
| 5. Channels | Email, SMS, WhatsApp, push, in-app, direct mail: roles and orchestration | SMS repeating email content at higher cost |
| 6. Deliverability | Authentication, spam rate, bounces, list quality, sending patterns | DMARC missing or spam rate near Gmail's limit |
| 7. Content and offers | Relevance, clarity, design, discount dependency | Every flow leads with a discount, training customers to wait |
| 8. Measurement | Attribution windows, holdouts, cohort reporting | Last-touch email attribution claiming most revenue, no holdouts |

## Workflow

### Step 1. Map the lifecycle stages
Define the stages for this business, for example: subscriber, new customer, activated, repeat or engaged, at risk, lapsed, won back. For SaaS, add trial, activated, paying, expanding. Use events, not opinions, to define entry and exit for each stage.

### Step 2. Inventory flows and campaigns
List every automated flow and recurring campaign with its trigger, audience, exit criteria, messages, channel and 90-day results. Mark which stage each serves.

### Step 3. Find coverage gaps and overlaps
Plot flows against stages. Typical gaps: nothing between first purchase and second, nothing for at-risk customers, no sunset policy for inactive subscribers. Typical overlaps: welcome, browse abandonment and newsletter hitting the same person in one day.

### Step 4. Check data and consent
Confirm key events fire correctly (sample ten profiles), consent is recorded per channel with source and timestamp, and suppression lists sync across tools.

### Step 5. Check deliverability basics
SPF, DKIM and DMARC aligned; one-click unsubscribe headers present on marketing mail; spam rate in Google Postmaster Tools well below 0.3% and ideally below 0.1%; bounce rate low; inactive subscribers suppressed. Route problems to `email-deliverability`.

### Step 6. Review content and offers
Sample the top flows. Check message clarity, personalisation that uses real data, mobile rendering, accessibility and how often discounts appear.

### Step 7. Review measurement
How is revenue attributed? What windows are used? Are there holdout groups? Compare flow-attributed revenue with incrementality evidence where any exists.

### Step 8. Score and prioritise
Score each layer 0 to 3. Rank fixes by revenue at stake, effort and risk. Produce a 90-day plan.

## Scoring rubric
| Score | Meaning |
|---|---|
| 0 | Missing or broken (no onboarding, no consent records, failing authentication) |
| 1 | Present but weak (one-email flows, open-based engagement, last-touch only) |
| 2 | Solid (stage coverage, clean data, basic holdouts) |
| 3 | Strong (orchestrated across channels, incrementality measured, preferences respected) |

## Benchmarks to use with care
Benchmarks vary hugely by industry, list source and platform, and many published figures come from vendors measuring their own customers. Use them to spot outliers, not to set targets. Your own trend and holdout results matter more. Open rates in particular are unreliable since Apple Mail Privacy Protection (2021) pre-loads images for many Apple Mail users; judge engagement on clicks, conversions and replies.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| B2B with long sales cycles | Add sales handoff, lead scoring and account-level views; measure pipeline, not just opens |
| Very small list | Focus on onboarding and a few high-value flows; skip complex segmentation |
| Marketplace with two sides | Audit buyer and seller lifecycles separately |
| Mid-migration between platforms | Audit both; freeze new flow builds until data and consent are mapped |
| Regulated industry (finance, health) | Check content approvals, consent wording and record-keeping first |
| Emerging markets where WhatsApp leads | Treat WhatsApp as a primary channel and audit template categories and costs |

## Handoffs to specialist skills
- Stage and journey design: `customer-journey-mapping`
- Segments and engagement tiers: `lifecycle-segmentation`
- Data quality: `crm-data-hygiene`
- B2B qualification and sales handoff: `lead-scoring-routing`
- New-customer programmes: `onboarding-activation`
- At-risk customers: `retention-churn-prevention`
- Lapsed customers: `win-back-reactivation`
- Inbox placement: `email-deliverability`
- Message quality: `lifecycle-email-copy-design`
- SMS and WhatsApp: `sms-whatsapp-lifecycle`
- Testing and holdouts: `lifecycle-experimentation`
- Reporting: `lifecycle-reporting-attribution`

## Worked example
A DTC skincare brand with 180,000 subscribers attributed 32% of revenue to email. The audit found a three-email welcome flow, abandoned cart and browse flows, a weekly newsletter and nothing else. There was no post-purchase education, no replenishment reminder for products that run out in about 60 days, no sunset policy, and engagement was defined by opens. Spam rate sat at 0.22% in Postmaster Tools, and every flow led with a discount. A one-month holdout on the cart flow showed its true incremental lift was about a third of what attribution claimed. The 90-day plan added post-purchase and replenishment flows, a sunset policy that suppressed 40,000 long-inactive subscribers, click-based engagement tiers, discount-free first messages and holdouts on every core flow. Spam rate fell below 0.1% and repeat purchase rate rose over the following quarter.

## Output format
```
# Lifecycle audit: <business>, <date>
## Summary (3 sentences: biggest risk, biggest opportunity, first move)
## Lifecycle map: stages with entry and exit events
## Coverage matrix: stages x flows (gaps and overlaps marked)
## Layer scores
| Layer | Score 0-3 | Key findings | Evidence |
## 90-day plan
| # | Action | Layer | Revenue at stake | Effort | Skill | Owner | Re-check |
```

## Common mistakes
- Judging engagement on open rates.
- Trusting platform-attributed revenue without holdouts.
- Adding flows without exit and priority rules.
- Ignoring deliverability until revenue drops.
- Treating consent as a checkbox instead of a preference system.

## Questions to ask before you recommend changes
- Which customer behaviour best predicts long-term value?
- What does a holdout test say about current flows, if anything?
- Who owns each flow, and who approves changes?
- What are the legal requirements in each market you send to?

## Self-check before you answer
- Did I map stages from events and check coverage at each stage?
- Did I check deliverability and consent before content?
- Did I separate attributed revenue from incremental evidence?
- Does every action have a skill, owner and re-check date?

## Official documentation
- Gmail email sender guidelines: https://support.google.com/a/answer/81126
- Yahoo sender best practices: https://senders.yahooinc.com/best-practices/
- Microsoft Outlook.com requirements for high-volume senders (Microsoft Defender for Office 365 blog, April 2025): https://techcommunity.microsoft.com/
- Google Postmaster Tools: https://postmaster.google.com/
- RFC 8058 one-click unsubscribe: https://www.rfc-editor.org/rfc/rfc8058

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-marketing-audit/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
