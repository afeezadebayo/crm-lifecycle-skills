---
name: lead-scoring-routing
description: "Build B2B lead scoring and routing from closed-won data: signed-off lifecycle stage definitions (MQL, SAL, SQL), separate fit and intent scores with decay, a fit by intent action matrix, product-qualified lead signals, routing by territory, segment, ownership and capacity, speed-to-lead service levels, sales feedback loops and nurture for everyone below threshold in HubSpot or Salesforce. Use whenever someone asks about lead scoring, MQL definitions, lead routing, sales and marketing alignment, lead quality complaints, speed to lead, product-qualified leads or why marketing leads don't turn into pipeline."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lead-scoring-routing/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Lead Scoring and Routing

In B2B, lifecycle marketing meets sales at one point: deciding which leads are ready for a conversation, who should have it, and what happens to everyone else. Poor scoring sends sales people who downloaded one ebook and ignores the account that visited pricing five times. Poor routing leaves hot leads waiting days, or sends them to the wrong rep. Both waste the budget that created the leads.

This skill builds a scoring model from closed-won data, defines lifecycle stages sales and marketing both accept, and designs routing and service levels so the right lead reaches the right person quickly, while everyone else gets nurtured.

## Operating principles
1. **Score from outcomes.** Weights come from what closed-won customers did and looked like, not from what feels important.
2. **Separate fit from intent.** Fit (who they are) and intent (what they did) answer different questions; combine them deliberately.
3. **Decay old behaviour.** A pricing visit last week matters; one last year doesn't.
4. **Agree definitions in writing.** MQL, SQL and SAL mean nothing unless sales and marketing sign the same definitions.
5. **Speed matters.** Response time to high-intent leads is one of the biggest controllable factors in conversion. [Consensus from sales research]

## Fit and intent
| Dimension | Signals | Example weights (illustrative) |
|---|---|---|
| Fit: firmographic | Industry, company size, region, tech stack | Target industry +15; under 10 employees -20 |
| Fit: person | Role, seniority, department | Decision-maker role +20; student -30 |
| Intent: high | Pricing page visits, demo request, trial sign-up, product usage in trial | Demo request: route immediately |
| Intent: medium | Case study views, webinar attendance, comparison pages | +10 each, decaying |
| Intent: low | Blog visits, newsletter clicks | +2 each, decaying |
| Negative | Competitor domain, job seeker, unsubscribed, personal email (sometimes) | Exclude or subtract |

Weights must be calibrated on your own data; the numbers above only illustrate structure.

## When to use, and when not to
Use it for B2B and high-consideration B2C (finance, property, education) when sales complain about lead quality, when leads wait too long, when MQL volume rises but pipeline doesn't, or when moving CRM.

Don't use it for self-serve products where no salesperson is involved (use `onboarding-activation` and product-qualified signals instead) or to clean the data first (`crm-data-hygiene`).

## Inputs to ask for, in one message
1. CRM (HubSpot, Salesforce) and marketing automation setup.
2. Closed-won and closed-lost deals for 12 to 24 months with contact and account properties and activity history.
3. Current lifecycle stage definitions and scoring rules.
4. Sales team structure: territories, segments, round-robin rules, capacity.
5. Current speed-to-lead and conversion rates by stage.
6. Product usage data if there's a free trial or freemium plan.

## Workflow

### Step 1. Agree stage definitions
Write definitions for lead, MQL (marketing qualified), SAL (sales accepted), SQL (sales qualified), opportunity and customer, with entry criteria and owner for each. Get both teams to sign off.

### Step 2. Analyse closed-won patterns
Compare won, lost and never-converted leads: firmographics, roles, sources, pages visited, content consumed, product usage. Identify the signals that separate them.

### Step 3. Build the model
Separate fit and intent scores. Use a matrix (fit A to D, intent 1 to 4) rather than one blended number, so a perfect-fit account with no intent gets nurture, and a high-intent poor-fit lead gets a lighter touch.

| | Intent high | Intent medium | Intent low |
|---|---|---|---|
| Fit A | Route to AE now | SDR outreach | Account-based nurture |
| Fit B | SDR outreach | Nurture plus SDR | Nurture |
| Fit C | Self-serve or partner | Nurture | Nurture |
| Fit D | Disqualify politely | Exclude | Exclude |

### Step 4. Add decay and thresholds
Reduce intent points over time (for example halve after 30 days). Set the MQL threshold where historical conversion to opportunity justifies sales time.

### Step 5. Design routing
Rules by territory, segment, account ownership (existing accounts go to their owner), language and capacity. Use round-robin within teams, with fallbacks for absence.

### Step 6. Set service levels
Response times by lead type (for example demo requests within business hours the same day), follow-up attempts, and when a lead returns to nurture.

### Step 7. Build feedback loops
Sales reject reasons recorded in a picklist; weekly review of rejected MQLs; quarterly recalibration of weights against new closed-won data.

### Step 8. Nurture the rest
Leads below threshold enter nurture tracks by fit and interest, with clear re-entry rules when intent rises.

## Product-qualified leads
For products with trials or free plans, usage signals (seats added, key feature used, usage limit reached) often predict buying better than marketing activity. Define product-qualified lead criteria with product and sales teams, and route accounts that hit them.

## Sales reject reasons picklist
| Reason | What it tells marketing |
|---|---|
| Not the decision-maker | Adjust role weights or add account-based routing |
| Company too small | Raise the fit threshold for size |
| No current need | Intent signals may be weak or decayed too slowly |
| Already a customer | Routing should check account ownership first |
| Student or job seeker | Add negative signals or form questions |
| Unreachable | Data quality or phone capture problem |
| Competitor | Exclude competitor domains |
Review rejected MQLs weekly for the first two months after launch, then monthly.

## Speed-to-lead playbook
- High-intent forms (demo, contact sales) create a task and an alert to the assigned rep immediately.
- Use scheduling links on the thank-you page so prospects can book straight away.
- Out-of-hours leads get an automatic, human-sounding reply with booking options.
- Measure median and 90th-percentile response time by rep and by lead source.
- Escalate to a team lead if a high-intent lead is untouched past the service level.

## Calibration check (quarterly)
1. Pull leads created in the last two quarters with their scores at MQL.
2. Compare conversion to opportunity and to closed-won by score band.
3. If a lower band converts nearly as well as a higher one, the threshold or weights need adjusting.
4. Check each signal's contribution: remove ones that no longer separate won from lost.
5. Document changes and tell sales what changed and why.

## Account-based routing basics
- Match leads to existing accounts by domain before any round-robin.
- If the account has an owner, route to them, even if the lead's score is low.
- For target accounts without an owner, assign by territory and notify the account team.
- Group multiple contacts from one account into one opportunity view.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Many contacts from one account | Score and route at account level; avoid several reps contacting the same company |
| Personal email addresses | Don't auto-disqualify in markets or segments where they're common; use other fit signals |
| Very low lead volume | Simple rules and manual review beat complex models |
| Inbound demo from a poor-fit company | Route to a lighter process (self-serve, partner) rather than ignoring |
| Sales ignores MQLs | Check speed-to-lead and reject reasons before changing the model |
| AI or vendor predictive scores | Validate against your outcomes and keep the explanation visible to reps |

## Handoffs to related skills
- Clean data and enrichment: `crm-data-hygiene`
- Journey stages: `customer-journey-mapping`
- Nurture content: `lifecycle-email-copy-design`
- Trial users: `onboarding-activation`
- Funnel reporting: `lifecycle-reporting-attribution`

## Worked example
A B2B analytics company sent 600 MQLs a month to sales, who accepted fewer than a third. Analysis of 18 months of deals showed webinar attendance and ebook downloads barely predicted wins, while pricing visits, integration page views and company size between 50 and 1,000 employees did. A fit and intent matrix with 30-day decay replaced the single score. Demo requests went straight to account executives with a same-day service level, and existing accounts routed to their owners. MQL volume fell to 220 a month, sales acceptance rose to most of them and pipeline from inbound grew.

## Output format
```
# Lead scoring and routing plan: <business>, <date>
## Stage definitions (signed off)
## Closed-won analysis (signals that predict wins)
## Scoring model: fit and intent criteria, weights, decay, thresholds
## Fit x intent action matrix
## Routing rules and service levels
## Feedback loop and recalibration schedule
## Nurture tracks for below-threshold leads
```

## Common mistakes
- Weights based on opinion rather than closed-won data.
- One blended score that hides poor fit or missing intent.
- No decay, so old activity keeps leads hot forever.
- No agreed definitions, so teams argue about lead quality.
- Slow follow-up on high-intent leads.

## Questions to ask before you build
- What does a closed-won customer look like, by data?
- How fast does sales respond today, by lead type?
- Who owns stage definitions and recalibration?

## Self-check before you answer
- Are fit and intent separate and based on outcomes?
- Is there decay and a threshold tied to conversion?
- Are routing rules and service levels explicit?
- Is there a feedback loop with sales?

## Official documentation
- HubSpot lead scoring: https://knowledge.hubspot.com/
- Salesforce lead assignment rules: https://help.salesforce.com/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lead-scoring-routing/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
