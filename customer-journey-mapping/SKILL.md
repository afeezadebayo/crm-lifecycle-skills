---
name: customer-journey-mapping
description: "Build a lifecycle journey map from behaviour data and customer research: stages with measurable entry and exit events and windows, the value moment that predicts retention, time between stages, stalls and drop-offs, touchpoints outside marketing, and a blueprint of triggers, messages, channels, priority and suppression rules for e-commerce, subscription, SaaS and marketplaces. Use whenever someone asks to map the customer journey, define lifecycle stages, find the activation metric or aha moment, design a lifecycle blueprint, or fix flows that overlap because stages were never agreed."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/customer-journey-mapping/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Customer Journey Mapping for Lifecycle

A lifecycle programme is only as good as its map of the customer. Most teams map the journey they wish customers took: sign up, onboard, buy, buy again. Real customers stall, skip steps, come back months later, buy for someone else or use the product in ways nobody planned. Journeys built on the wishful version send the wrong message at the wrong time.

This skill builds a lifecycle map from behaviour data and customer research, defines each stage with measurable entry and exit events, finds the moments that predict long-term value, and turns the map into a blueprint of triggers, messages and channels.

## Operating principles
1. **Events, not assumptions.** Every stage has an entry event, an exit event and a time window.
2. **Find the value moment.** The action that best predicts retention (first project created, second purchase, team invite) becomes the centre of the map.
3. **Map stalls as carefully as progress.** Where people get stuck is where lifecycle work pays most.
4. **One customer, many paths.** Include branches for different segments, intents and product lines.
5. **Add the customer's voice.** Data shows what happens; interviews and support tickets show why.

## When to use, and when not to
Use it before building or rebuilding a lifecycle programme, when launching a new product line, when retention curves flatten early, or when flows overlap because nobody agreed what each stage is.

Don't use it to define segments in detail (`lifecycle-segmentation`) or to design one programme's messages (`onboarding-activation`, `retention-churn-prevention`, `win-back-reactivation`).

## Inputs to ask for, in one message
1. Product and business model, and the main customer types.
2. Event data: sign-up, key product actions, purchases, renewals, cancellations, with timestamps (or exports from analytics, CDP or product analytics such as Amplitude or Mixpanel).
3. Cohort retention curves by sign-up month and by acquisition source.
4. Customer research: interviews, surveys, support tickets, reviews, sales notes.
5. Current flows and campaigns with their triggers.

## Workflow

### Step 1. Draft stages
Start with a generic set, then adapt:
| Model | Typical stages |
|---|---|
| E-commerce | Visitor, subscriber, first purchase, second purchase, loyal, at risk, lapsed |
| Subscription | Trial or sign-up, activated, paying, habitual, at risk, cancelled, won back |
| SaaS B2B | Lead, MQL, SQL, trial, activated account, paying, expanding, renewal, churned |
| Marketplace | Separate maps for buyers and sellers, linked at the transaction |

### Step 2. Define entry and exit events
For each stage, write the event that moves someone in and the one that moves them out, plus a time limit ("activated = created first project within 14 days of sign-up").

### Step 3. Find the value moment
Compare retention for users who did and didn't take candidate actions in their first days or weeks. The action with the strongest link to long-term retention, and that the business can influence, becomes the activation target. Treat this as correlation and validate it with an experiment later.

### Step 4. Measure time between stages
Median and distribution of time from sign-up to first value, first to second purchase, renewal to expansion. These windows set when messages should fire.

### Step 5. Map stalls and drop-offs
Where do most people stop? What do support tickets and interviews say about why? List the friction at each stall.

### Step 6. Add channels and touchpoints
For each stage, note the touchpoints that exist outside marketing: product UI, sales calls, support, invoices, delivery notifications. Lifecycle messages should complement them, not duplicate them.

### Step 7. Build the blueprint
For each stage and stall: the goal, trigger, audience, message intent, channel, timing, exit rule and metric.

### Step 8. Agree ownership
Assign an owner per stage and a priority order for when someone qualifies for several journeys.

## Journey blueprint template
```
| Stage | Entry event | Exit event | Window | Goal | Stall points | Triggered messages (channel, timing) | Priority | Metric | Owner |
```

## Priority and suppression rules
When someone qualifies for more than one journey, decide which wins:
1. Transactional and service messages always send.
2. Onboarding beats promotional campaigns for new customers.
3. At-risk and win-back journeys suppress general newsletters for their duration.
4. A global frequency cap (for example no more than one marketing message per day per channel) applies across journeys.

## Finding the value moment: method
1. List five to ten candidate actions users can take early (create, import, invite, connect an integration, buy a second item, use a feature).
2. For each, split new users into those who took the action within the first 7 or 14 days and those who didn't.
3. Compare retention at day 30, 60 or 90 (or repeat purchase within 90 days for e-commerce).
4. Check volume: an action only a tiny share of users take is a poor target even if retention is high.
5. Check influence: can onboarding realistically get more people to do it?
6. Pick one primary action and, if needed, a threshold ("three tasks", "two purchases").
7. Plan an experiment that pushes more users towards the action and measures retention against a holdout.

| Candidate action | Share who did it in 7 days | 90-day retention if done | 90-day retention if not | Influenceable? |
|---|---|---|---|---|
| Created 3 dated tasks | 28% | high | low | Yes, through onboarding |
| Invited a teammate | 12% | high | medium | Partly |
| Connected calendar | 6% | high | medium | Yes, but small volume |

## Customer interview guide (30 minutes)
- What were you trying to get done when you signed up or first bought?
- What did you try before us?
- Walk me through your first week. Where did you get stuck?
- When did it start to feel useful, if it did?
- What almost made you stop?
- What would make you recommend us, or leave?
Interview recent customers, recent churners and long-term loyal customers separately; their answers differ in useful ways.

## Example blueprint row
| Stage | Entry | Exit | Window | Goal | Stall | Messages | Priority | Metric |
|---|---|---|---|---|---|---|---|---|
| New trial | Signed up | Created 3 dated tasks | 14 days | Reach first value | No task in 48h | Day 0 email (how to start), 48h in-app prompt, day 3 email with template, day 7 check-in from a person | Above all marketing | Activation rate within 14 days |

## Journey health metrics
- Conversion rate between consecutive stages.
- Median time between stages.
- Share of customers stalled at each stage for longer than the window.
- Retention by stage reached in the first 30 days.
- Message load per customer per week by stage, to catch over-messaging.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Purchase cycle longer than a year | Use engagement events between purchases (content, account visits) as interim stages |
| Gifting and one-off buyers | Separate them early; don't push replenishment on gift buyers |
| Free plan with no upgrade pressure | Define "habitual" by usage, and map upgrade triggers to usage limits |
| Several products | Map shared stages once, with product-specific branches |
| Little event data | Start with interviews and purchase data; instrument the key events before building complex journeys |

## Handoffs to related skills
- Overall programme review: `lifecycle-marketing-audit`
- Segment definitions: `lifecycle-segmentation`
- Event and field quality: `crm-data-hygiene`
- Programmes per stage: `onboarding-activation`, `retention-churn-prevention`, `win-back-reactivation`
- Validating the value moment: `lifecycle-experimentation`

## Worked example
A project management SaaS believed activation meant inviting a teammate. Comparing 90-day retention showed users who created three tasks with due dates in their first week retained far better than those who only invited teammates. Interviews explained it: solo users set up their own work before involving anyone. The new map made "three dated tasks in seven days" the activation target, added a stall branch for users who signed up but created nothing in 48 hours, and moved the invite prompt to after first value. Onboarding messages were rebuilt around that sequence, and a holdout test later confirmed the new activation rate rose.

## Output format
```
# Lifecycle journey map: <business>, <date>
## Stages with entry and exit events and windows
## Value moment analysis (candidate actions, retention comparison, chosen target)
## Time between stages
## Stalls and friction (with evidence)
## Journey blueprint (table)
## Priority and suppression rules
## Owners
```

## Common mistakes
- Defining stages by opinion rather than events.
- Choosing an activation metric because it's easy to track, not because it predicts retention.
- Ignoring touchpoints outside marketing.
- Building journeys without priority rules, so customers get everything at once.
- Treating correlation as proven cause.

## Questions to ask before you map
- Which customer behaviour does the business believe predicts retention, and what does the data say?
- Which events are reliably tracked today?
- Who owns product messaging versus marketing messaging?

## Self-check before you answer
- Does every stage have entry and exit events and a window?
- Is the value moment backed by retention data and labelled as correlation?
- Are stalls mapped with evidence?
- Are priority, suppression and frequency rules defined?

## Further reading
- Amplitude, product analytics and retention analysis guides: https://amplitude.com/blog
- Reforge, retention and engagement frameworks: https://www.reforge.com/blog

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/customer-journey-mapping/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
