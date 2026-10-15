---
name: lifecycle-segmentation
description: "Build segments that drive action: lifecycle stages, engagement tiers based on clicks, purchases and logins rather than Apple-inflated opens, RFM and value groups, intent and preference segments, B2B fit, an action matrix for journeys, frequency, offers and channels, and a sunset policy that protects deliverability. Use whenever someone asks about email segmentation, customer segments, RFM analysis, engagement tiers, sunset policies, who to send to, list cleaning by engagement, or why every subscriber gets every campaign."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-segmentation/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Lifecycle Segmentation and Engagement Tiers

Segmentation decides who gets which message. Done well, it means new customers hear about getting started, loyal customers hear about what's new, at-risk customers get help and lapsed subscribers stop receiving mail they ignore. Done badly, everyone gets everything, engagement falls, complaints rise and inbox placement suffers.

This skill builds segments that are simple enough to maintain, based on behaviour rather than opens, and tied to actions: who to message, how often, with what, and who to suppress.

## Operating principles
1. **Behaviour beats demographics.** What people did recently predicts what they'll do next better than who they are.
2. **Clicks, purchases and logins over opens.** Apple Mail Privacy Protection pre-loads images for many Apple Mail users, so opens are inflated and unreliable for engagement.
3. **Every segment needs an action.** If no message, offer or suppression changes for a segment, it doesn't need to exist.
4. **Fewer, durable segments.** A handful of well-defined segments used everywhere beats dozens of one-off lists.
5. **Suppression is a segment too.** Deciding who not to mail protects deliverability and goodwill.

## Core segment families
| Family | Examples | Typical use |
|---|---|---|
| Lifecycle stage | New, activated, repeat, loyal, at risk, lapsed | Which journey someone is in |
| Engagement tier | Engaged (clicked or bought in 30 days), warm (90 days), cold (180 days), inactive (over 180 days) | Frequency and sunset rules |
| Value | RFM (recency, frequency, monetary), predicted lifetime value, plan tier | Offers, service level, VIP treatment |
| Intent | Browsed category, abandoned cart, viewed pricing, used feature X | Triggered messages |
| Preference | Topics chosen, channel preference, frequency choice | Respecting what people asked for |
| B2B fit | Industry, company size, role, account stage | Content relevance and sales handoff |

## RFM in practice
Score each customer 1 to 5 on recency (days since last purchase), frequency (number of purchases) and monetary value (total spend), using quintiles from your own data. Then group:

| Group | RFM pattern | Action |
|---|---|---|
| Champions | High R, high F, high M | Early access, referrals, reviews; avoid discounts |
| Loyal | Medium to high R and F | Cross-sell, loyalty perks |
| Promising new | High R, low F | Second-purchase journey |
| At risk | Low R, high F or M | Win-back with service first, offer second |
| Hibernating | Low R, low F | Low-frequency reactivation, then sunset |

## When to use, and when not to
Use it when everyone receives the same campaigns, when engagement and deliverability are falling, before personalisation projects, and when moving platforms.

Don't use it to map stages from scratch (`customer-journey-mapping`) or to clean the underlying data (`crm-data-hygiene`).

## Inputs to ask for, in one message
1. Platform and available data: events, purchases, product usage, preferences.
2. List size and engagement distribution (last click, last purchase, last login).
3. Current segments and how they're used.
4. Revenue by customer group, if available.
5. Any regional or consent rules that limit targeting.

## Workflow

### Step 1. Audit current segments
List every saved segment, its definition, size, last use and owner. Archive anything unused for 90 days.

### Step 2. Define engagement tiers on reliable signals
Use clicks, purchases, logins, replies and site visits. If you must use opens, combine them with another signal and exclude machine opens where your platform flags them.

### Step 3. Define lifecycle stages
Reuse the journey map's entry and exit events so segments and journeys agree.

### Step 4. Add value and intent
Calculate RFM or predicted value; add intent segments for triggered flows.

### Step 5. Attach actions
For each segment: journeys it enters, campaign frequency, offer policy, channel mix and suppression rules.

### Step 6. Set a sunset policy
For subscribers with no clicks, purchases or visits for a set period (often 90 to 180 days, depending on purchase cycle), send a short re-permission sequence, then suppress those who don't respond.

### Step 7. Monitor
Track segment sizes and movement monthly: how many move from new to repeat, from engaged to cold, from at risk to won back.

## Segment definition template
```
Name: Engaged subscribers
Definition: clicked an email OR purchased OR logged in within the last 30 days, AND marketing consent = true
Refresh: daily
Used for: weekly campaigns at full frequency; product launches
Excludes: suppressed, bounced, complained
Owner: lifecycle lead
```

## Frequency rules by tier
| Tier | Campaign frequency | Triggered flows | Notes |
|---|---|---|---|
| Engaged (30 days) | Full schedule | All | Best audience for launches and tests |
| Warm (31 to 90 days) | Reduced (for example half) | All | Lead with best-performing content |
| Cold (91 to 180 days) | Monthly digest or highlights | Purchase-triggered only | Watch complaint rates closely |
| Inactive (over 180 days) | None until re-permission | Transactional only | Re-permission, then suppress |
Adjust the windows to your purchase cycle: a grocery brand might use 14, 45 and 90 days; a furniture brand 60, 180 and 365.

## Re-permission sequence
1. **Email 1:** "Do you still want to hear from us?" with a clear keep-me button and a preference link to choose topics or lower frequency.
2. **Email 2 (5 to 7 days later):** a short reminder showing what they get, with the same button.
3. **Email 3 (5 to 7 days later):** "We'll stop emailing you on [date] unless you click."
4. **Suppress** non-responders from marketing; keep transactional mail. Allow easy re-subscription on site.

## RFM calculation example (SQL)
```sql
WITH c AS (
  SELECT customer_id,
         DATE_DIFF(CURRENT_DATE(), MAX(order_date), DAY) AS recency_days,
         COUNT(*) AS frequency,
         SUM(order_value) AS monetary
  FROM orders
  WHERE order_date >= DATE_SUB(CURRENT_DATE(), INTERVAL 24 MONTH)
  GROUP BY customer_id
)
SELECT customer_id,
       6 - NTILE(5) OVER (ORDER BY recency_days) AS r_score,
       NTILE(5) OVER (ORDER BY frequency) AS f_score,
       NTILE(5) OVER (ORDER BY monetary) AS m_score
FROM c;
```
Recalculate weekly or monthly and sync scores to the messaging platform as profile properties.

## Preference centre essentials
- Topic choices that map to real content streams.
- Frequency options (for example weekly or monthly digest).
- Channel choices (email, SMS, WhatsApp, push) with separate consent.
- A pause option for a set period.
- Unsubscribe from all marketing, clearly visible.
Preferences only build trust if campaigns actually respect them, so wire every preference to a segment rule.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Long purchase cycles (furniture, cars) | Use content engagement and site visits for tiers; lengthen the sunset window |
| B2B accounts with many contacts | Segment at account and contact level; don't sunset a champion because colleagues ignore mail |
| Very small list | Use three or four segments at most |
| Strong privacy rules in a market | Limit profiling to what consent covers; document the basis |
| Predicted LTV from a vendor model | Check it against actual outcomes before using it for offers |

## Handoffs to related skills
- Stage definitions: `customer-journey-mapping`
- Data quality: `crm-data-hygiene`
- Sunset and inbox placement: `email-deliverability`
- At-risk and lapsed programmes: `retention-churn-prevention`, `win-back-reactivation`
- Testing segment-based changes: `lifecycle-experimentation`

## Worked example
An online bookshop sent every campaign to 240,000 subscribers. Defining engagement on clicks and purchases showed only 52,000 had engaged in 90 days, while 110,000 had not clicked or bought in over a year. The new model used four engagement tiers, RFM groups and genre preferences. Campaigns went to engaged and warm tiers at full frequency, cold subscribers received a monthly digest, and inactive subscribers got a three-email re-permission sequence before suppression. Complaint rates fell, Gmail inbox placement improved and revenue per send rose because messages matched interests.

## Output format
```
# Segmentation plan: <business>, <date>
## Current segment audit (keep, merge, archive)
## Segment definitions (name, logic, refresh, owner)
## Action matrix
| Segment | Journeys | Campaign frequency | Offer policy | Channels | Suppression |
## Sunset policy
## Monitoring metrics
```

## Common mistakes
- Engagement based on opens alone.
- Dozens of segments nobody maintains.
- Segments with no change in treatment.
- No sunset policy, so inactive addresses damage deliverability.
- Discounting champions who would buy anyway.

## Questions to ask before you segment
- Which signals are reliable on your platform?
- How long is a normal gap between purchases or visits?
- Who will maintain segment definitions?

## Self-check before you answer
- Are engagement tiers based on reliable signals?
- Does every segment have a clear action?
- Is there a sunset policy matched to the purchase cycle?
- Are definitions documented with refresh and owner?

## Further reading
- Apple Mail Privacy Protection overview: https://support.apple.com/guide/mail/use-mail-privacy-protection-mlhl03be2866/mac
- Klaviyo, RFM analysis guide: https://help.klaviyo.com/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/lifecycle-segmentation/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
