---
name: lifecycle-reporting-attribution
description: "Build lifecycle reporting leadership can trust: a metric dictionary, health, engagement, attributed, incremental and customer outcome layers, clear labels for attribution models and windows, UTM and order ID tracking, reconciliation with finance, cohort retention and lifetime value views, holdout-based incrementality and monthly decision-focused dashboards. Use whenever someone asks about email reporting, lifecycle KPIs, email attribution, Klaviyo or Braze revenue reports, CRM dashboards, cohort retention reports or why marketing and finance numbers disagree."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-reporting-attribution/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Lifecycle Reporting and Attribution

Lifecycle dashboards are often full of numbers that flatter the channel: opens inflated by Apple Mail Privacy Protection, revenue attributed to any email clicked or opened within days of a purchase, and flow totals that add up to more than the business actually made. Leadership either believes them and over-invests, or stops trusting lifecycle reporting altogether.

This skill builds reporting that holds up: clear definitions, metrics that reflect customer behaviour, attribution that is labelled for what it is, incrementality from holdouts, and cohort views that show whether lifecycle work changes retention and lifetime value.

## Operating principles
1. **Define every metric.** Write how each number is calculated, from which source, with which window.
2. **Separate activity, attributed and incremental.** Sends and clicks are activity; platform revenue is attributed; holdout differences are incremental.
3. **Retire unreliable metrics.** Opens are not a reliable engagement or success metric on their own.
4. **Report cohorts, not just campaigns.** Retention and lifetime value by cohort show whether the programme works over time.
5. **Tie to business outcomes.** Revenue, retention, activation and pipeline, not vanity metrics.

## Metric layers
| Layer | Metrics | Use |
|---|---|---|
| Health | Deliverability (spam rate, bounces), list growth, consent coverage, unsubscribe and complaint rates | Keep the channel working |
| Engagement | Clicks, click-to-conversion, replies, site visits from messages | Message quality |
| Attributed outcomes | Platform-attributed conversions and revenue (state window and model) | Directional, compare flows |
| Incremental outcomes | Holdout lift in conversions, revenue, retention | True contribution |
| Customer outcomes | Retention curves, repeat purchase rate, activation rate, net revenue retention, lifetime value by cohort | Long-term impact |

## Attribution models and their limits
| Model | How it works | Limitation |
|---|---|---|
| Platform default (for example click or open within a set number of days) | Credits the message for any purchase in the window | Over-credits; double counts across channels |
| Last click (analytics) | Credits the last clicked source | Under-credits lifecycle that nudged earlier |
| Multi-touch | Spreads credit across touchpoints | Depends on tracking quality; still not causal |
| Holdout-based incrementality | Compares treated and untreated groups | Needs volume and patience; the most reliable |
Tell leadership which model each number uses, and use holdouts for budget decisions.

## When to use, and when not to
Use it to build or rebuild lifecycle dashboards, prepare leadership reporting, reconcile platform revenue with finance, and set KPIs for a new programme.

Don't use it to design tests (`lifecycle-experimentation`) or audit the whole programme (`lifecycle-marketing-audit`).

## Inputs to ask for, in one message
1. Platforms and their attribution settings (windows, open versus click).
2. Analytics setup (GA4 or similar) and UTM conventions.
3. Revenue and order data from finance or the commerce platform.
4. Customer data for cohorts: first purchase date, subsequent orders, subscription events.
5. Holdout results, if any.
6. Who reads the reports and what decisions they make.

## Workflow

### Step 1. Agree definitions
A metric dictionary: name, formula, source, window, owner. Include "attributed revenue (platform, 5-day click)" style labels.

### Step 2. Fix tracking
Consistent UTMs on every link (source, medium, campaign, content), conversion events in analytics, and order IDs linking platform data to finance.

### Step 3. Reconcile
Compare platform-attributed revenue with analytics and finance totals. Explain gaps (windows, double counting, view-through credit).

### Step 4. Build the dashboard
One page per audience: health and engagement for the lifecycle team, incremental and customer outcomes for leadership.

### Step 5. Add cohorts
Retention and repeat purchase by first-purchase month; activation and retention by sign-up month; compare cohorts before and after major lifecycle changes.

### Step 6. Add incrementality
For flows with holdouts, report incremental revenue and profit next to attributed revenue.

### Step 7. Review monthly
What changed, why, what we'll do next. Annotate launches, platform changes and seasonality.

## Leadership dashboard template
```
# Lifecycle report: <month>
## Summary (3 sentences)
## Customer outcomes: repeat purchase rate, retention by cohort, activation rate, NRR
## Incremental impact: holdout results by flow (revenue, profit, range)
## Attributed revenue (labelled with model and window) vs last month
## Channel health: spam rate, list growth, unsubscribes, complaints
## Decisions and next tests
```

## Metric dictionary example
| Metric | Formula | Source | Window | Owner |
|---|---|---|---|---|
| Click rate | Unique clickers ÷ delivered | Messaging platform | Per send | Lifecycle lead |
| Attributed revenue (click, 5 days) | Revenue from orders within 5 days of a click | Messaging platform | 5 days | Lifecycle lead |
| Incremental revenue | Revenue per person (treated minus holdout) × treated size | Holdout analysis | Test period | Analyst |
| Repeat purchase rate | Customers with 2+ orders within 90 days of first ÷ first-time customers | Commerce data | 90 days | CRM manager |
| Activation rate | New users reaching the activation event within window ÷ new users | Product analytics | 7 or 14 days | Growth lead |
| Spam rate | Spam reports ÷ delivered (Gmail) | Postmaster Tools | Daily | Deliverability owner |

## UTM convention
- utm_source: the platform or channel (klaviyo, braze, whatsapp)
- utm_medium: email, sms, whatsapp, push
- utm_campaign: flow or campaign name in a fixed format (flow_onboarding_v3, camp_2026-10-autumn-launch)
- utm_content: message and link position (msg2_cta_primary)
Write the convention down and apply it in templates so it can't be forgotten.

## Cohort retention view
```
| First-order month | Customers | Repeat within 30d | 60d | 90d | 180d |
| 2026-04 | 3,210 | 12% | 19% | 24% | 31% |
| 2026-05 | 3,480 | 13% | 21% | 27% | ... |
```
Mark the month a major lifecycle change launched; compare cohorts before and after, while allowing for seasonality and acquisition mix.

## Reconciliation checklist
1. Pull total online revenue for the month from finance.
2. Pull attributed revenue from each messaging platform and from analytics by channel.
3. Deduplicate by order ID across platforms.
4. Compare totals; list the reasons for gaps (windows, opens, view-through).
5. Agree one labelled number for leadership and keep the rest for the team.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Platform revenue exceeds total online revenue share that's plausible | Reconcile; report incremental figures for decisions |
| B2B with long cycles | Report influenced pipeline and stage conversion, not just closed revenue in the month |
| Several messaging platforms | Deduplicate conversions by order ID before summing |
| No holdouts yet | Label attributed numbers clearly and start one holdout on the biggest flow |
| Finance and marketing numbers disagree | Agree which is the record for revenue; marketing reports influence, finance reports revenue |

## Handoffs to related skills
- Holdout design: `lifecycle-experimentation`
- Data quality: `crm-data-hygiene`
- Deliverability metrics: `email-deliverability`
- Programme review: `lifecycle-marketing-audit`
- Retention metrics: `retention-churn-prevention`

## Worked example
A homeware brand's Klaviyo dashboard credited email and SMS with 41% of online revenue using a five-day open or click window. Finance doubted it. Reconciliation showed double counting across email and SMS and heavy credit from opens. The new reporting used click-based attribution labelled as such, deduplicated by order ID, added holdout results for the three largest flows and showed repeat purchase rate by first-order cohort. The attributed share fell to a more plausible level, the incremental figures gave leadership numbers they trusted, and budget for post-purchase flows grew because their cohort impact was now visible.

## Output format
```
# Lifecycle reporting plan: <business>, <date>
## Metric dictionary
## Tracking fixes (UTMs, events, order IDs)
## Reconciliation findings
## Dashboard designs by audience
## Cohort views
## Incrementality reporting
## Review cadence and owners
```

## Common mistakes
- Open rate as a headline KPI.
- Summing attributed revenue across platforms.
- No labels for attribution models and windows.
- Campaign-only views with no cohorts.
- Reports that don't lead to decisions.

## Questions to ask before you build
- Which decisions will this report inform?
- What attribution settings does each platform use?
- Which revenue figure does finance consider the record?

## Self-check before you answer
- Is every metric defined with source and window?
- Are activity, attributed and incremental numbers separated?
- Are cohorts included?
- Does the report end with decisions?

## Further reading
- GA4 UTM and campaign tracking: https://support.google.com/analytics/answer/10917952
- Apple Mail Privacy Protection: https://support.apple.com/guide/mail/use-mail-privacy-protection-mlhl03be2866/mac

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-reporting-attribution/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
