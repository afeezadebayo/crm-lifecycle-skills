---
name: retention-churn-prevention
description: "Reduce churn before customers decide to leave: split voluntary and involuntary churn, fix failed payments with retries, card updaters and dunning, build and validate a health score from leading indicators, match interventions to churn reasons, design a fair cancellation flow with pause and downgrade options, build loyalty for healthy customers and measure saves against holdouts. Use whenever someone asks about churn, retention marketing, customer health scores, dunning, failed payments, cancellation flows, save offers, renewal campaigns or keeping subscribers."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/retention-churn-prevention/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Retention and Churn Prevention

Keeping a customer is usually cheaper than winning a new one, and small retention gains compound over time. Yet most retention work starts too late, with a discount offered on the cancellation page. By then the customer has decided. Churn prevention works best weeks earlier, when usage drops, a payment fails or a support ticket goes unresolved.

This skill builds early-warning signals, separates voluntary from involuntary churn, designs interventions matched to the reason, and proves which ones work with holdouts.

## Operating principles
1. **Understand why before acting.** Churn reasons differ: no value found, price, switching to a competitor, business closed, payment failure.
2. **Fix involuntary churn first.** Failed payments are often a large, easy share of subscription churn.
3. **Act on leading indicators.** Falling usage and unresolved issues come before cancellation.
4. **Service before discounts.** Help, education and the right plan often save more customers, at lower cost, than price cuts.
5. **Measure saves against a holdout.** Many "saved" customers would have stayed anyway.

## Types of churn
| Type | Example | Main levers |
|---|---|---|
| Involuntary | Expired card, failed payment | Card updater services, smart retries, dunning messages, in-app prompts |
| Voluntary: no value | Never activated or usage faded | Re-onboarding, use-case content, success outreach |
| Voluntary: price | Too expensive for value received | Right-size plan, annual option, pause |
| Voluntary: competitor | Switched for features or price | Feature education, roadmap, competitive offer where justified |
| Voluntary: circumstance | Seasonal business, closed company | Pause, downgrade, easy return later |
| Non-subscription lapse (e-commerce) | No repeat purchase in expected window | Replenishment, relevant recommendations, loyalty |

## When to use, and when not to
Use it for subscription businesses, SaaS, memberships, marketplaces with repeat buyers and e-commerce with repeat purchase potential, when churn rises or retention curves flatten.

Don't use it for customers who already left (`win-back-reactivation`) or for new customers (`onboarding-activation`).

## Inputs to ask for, in one message
1. Churn rate by month and cohort, split voluntary and involuntary if possible.
2. Cancellation reasons (exit survey, support notes, sales notes).
3. Usage data: logins, key actions, seats, order frequency.
4. Payment data: failure rates, retry logic, dunning messages.
5. Current retention flows and offers.
6. Customer success capacity for high-value accounts.

## Workflow

### Step 1. Size the problem
Split churn by type, plan, tenure, acquisition source and segment. Find where most revenue is lost.

### Step 2. Fix involuntary churn
Check payment retry schedules, card updater services from your payment provider, dunning emails and in-app banners, and grace periods. Measure recovery rate.

### Step 3. Build a health score
Combine leading indicators: usage trend, key feature adoption, support tickets, NPS or CSAT, billing issues, champion changes in B2B. Keep it simple and validate it against actual churn.

### Step 4. Design interventions by reason
Match each at-risk signal to an intervention: usage drop gets a re-onboarding sequence, unresolved ticket gets a support escalation, price sensitivity gets plan options, champion change gets an introduction to the new contact.

### Step 5. Improve the cancellation flow
Ask why (one question with options), offer the alternative that fits the reason (pause, downgrade, help), and make cancellation itself easy. Obstructive flows damage trust and can break consumer protection rules in several markets.

### Step 6. Build loyalty for the healthy majority
Recognition, early access, useful content and referral programmes for engaged customers reduce future churn.

### Step 7. Measure
Retention by cohort, save rate by intervention with holdouts, revenue retained, and involuntary recovery rate.

## Health score example
| Signal | Weight (illustrative) | Source |
|---|---|---|
| Usage down over 40% vs 4-week average | High | Product analytics |
| Key feature not used in 30 days | Medium | Product analytics |
| Open support ticket over 7 days | Medium | Help desk |
| Payment failed | High | Billing |
| Champion left (B2B) | High | CRM |
| Low NPS score | Medium | Survey |
Calibrate on your own churn data; validate that high-risk scores actually churn more.

## Dunning sequence (subscriptions)
| Timing | Channel | Message |
|---|---|---|
| Payment fails | Email + in-app | Clear, friendly notice with a one-click update link |
| Retry 1 fails (day 3) | Email | Reminder, what happens if not updated |
| Retry 2 fails (day 7) | Email + SMS (with consent) | Final notice before service changes |
| Grace period ends | Email | Account paused, easy reactivation |
Coordinate messages with the payment retry schedule so customers aren't asked to update a card that was just successfully retried.

## Cancellation flow design
1. **Ask one question:** why are you leaving? Offer five or six options plus "other".
2. **Offer the matching alternative:**
| Reason chosen | Offer |
|---|---|
| Too expensive | Smaller plan, annual billing or a time-limited price, if it makes business sense |
| Not using it enough | Pause for one to three months |
| Missing a feature | Show the workaround or roadmap; log the request |
| Technical problems | Connect to support immediately |
| Switching to a competitor | Ask which one; offer a short call for high-value accounts |
| Temporary situation | Pause |
3. **Confirm cancellation clearly** if they decline, with what happens next and how to return.
4. **Follow up** with a short survey or a personal note for high-value accounts.

## Interventions by health signal
| Signal | First response | If no change in 14 days |
|---|---|---|
| Usage drop | Re-onboarding email with the use case they started with | Customer success outreach (higher-value accounts) |
| Unused key feature | Short guide or video tied to their goal | Webinar invite or office hours |
| Long-open support ticket | Escalate and apologise | Manager follow-up |
| Champion left (B2B) | Introduce yourself to the new contact; offer a review | Executive sponsor contact |
| Repeated delivery skips | Offer pause or personalisation | Smaller plan |

## Retention metrics
| Metric | Definition |
|---|---|
| Logo churn | Share of customers lost in a period |
| Revenue churn | Share of recurring revenue lost |
| Net revenue retention | Revenue from a cohort including expansion, minus churn and contraction |
| Involuntary recovery rate | Failed payments later recovered |
| Save rate (incremental) | Saves in treatment minus saves in holdout |
| Repeat purchase rate | Share of customers buying again within the expected window (e-commerce) |

## Loyalty that reduces churn
- Recognise milestones (anniversaries, usage achievements) with something useful, not just a badge.
- Give engaged customers early access and a channel for feedback.
- Reward referrals in ways that help both sides.
- Avoid points schemes that cost more than the behaviour they change; test them against a holdout.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| B2B annual contracts | Start renewal work 90 to 120 days before the date, with usage reviews |
| Seasonal customers | Offer pause rather than treating seasonal gaps as churn |
| Heavy discount saves | Track whether saved customers churn again soon after the discount ends |
| Regulated cancellation rules | Follow local consumer law on easy cancellation and renewal reminders |
| Low-value plans at scale | Automate; reserve human outreach for high-value accounts |

## Handoffs to related skills
- Journey and stages: `customer-journey-mapping`
- At-risk segments: `lifecycle-segmentation`
- Re-onboarding: `onboarding-activation`
- Lapsed customers: `win-back-reactivation`
- SMS dunning and WhatsApp: `sms-whatsapp-lifecycle`
- Holdouts: `lifecycle-experimentation`
- Retention reporting: `lifecycle-reporting-attribution`

## Worked example
A meal-kit subscription had 9% monthly churn. Analysis showed almost a quarter was involuntary (failed cards), and most voluntary cancellations came in weeks 3 to 6 from customers who skipped two deliveries in a row. The team enabled card updater services and smarter retries, rebuilt dunning around the retry schedule, added a "skip pattern" trigger that offered pause and recipe personalisation, and changed the cancel flow to ask why and offer pause or a smaller box first. A holdout showed the skip-pattern intervention saved customers who otherwise would have left, and involuntary churn fell sharply.

## Output format
```
# Retention plan: <business>, <date>
## Churn breakdown (type, segment, tenure, revenue)
## Involuntary churn fixes
## Health score definition and validation
## Interventions by signal and reason
## Cancellation flow changes
## Loyalty programme for healthy customers
## Measurement with holdouts
```

## Common mistakes
- Only acting at the cancellation page.
- Ignoring failed payments.
- Discounts as the first and only offer.
- Health scores nobody validated.
- Counting every customer who stayed after an offer as saved.

## Questions to ask before you design
- What share of churn is involuntary?
- Which signals come before cancellation, and how early?
- What alternatives to cancelling can the business offer?

## Self-check before you answer
- Is churn split by type and reason?
- Are involuntary fixes in place first?
- Are interventions matched to reasons, not one offer for all?
- Are saves measured against holdouts?

## Further reading
- Stripe, reducing involuntary churn: https://stripe.com/resources/more
- Recurly and Chargebee subscription research libraries: https://recurly.com/research/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/retention-churn-prevention/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
