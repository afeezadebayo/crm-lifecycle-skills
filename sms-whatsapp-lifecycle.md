---
name: sms-whatsapp-lifecycle
description: "Use SMS and WhatsApp for the lifecycle moments that matter: channel roles by urgency and cost, explicit per-channel consent, US 10DLC registration, UK PECR, EU and Nigerian rules, WhatsApp template categories and per-message pricing since July 2025, utility and marketing flows, message copy, frequency caps, quiet hours, cost forecasts and incremental measurement. Use whenever someone asks about SMS marketing, WhatsApp marketing, WhatsApp Business API, text message flows, 10DLC, SMS consent, WhatsApp template pricing or adding messaging channels to lifecycle."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/sms-whatsapp-lifecycle/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# SMS and WhatsApp Lifecycle Messaging

SMS and WhatsApp reach people where they actually look: most messages are read within minutes. That power cuts both ways. Each message costs money, interrupts someone's day and needs explicit consent in most markets. Used well, these channels handle the moments that matter: delivery updates, appointment reminders, abandoned carts with real urgency, payment failures and conversations. Used badly, they become expensive spam that gets blocked.

This skill decides what belongs on SMS and WhatsApp, sets consent and compliance, designs message flows and templates, manages costs and measures incremental impact.

## Channel roles
| Channel | Strengths | Watch out for | Best for |
|---|---|---|---|
| SMS | Universal, fast, no app needed | Cost per message, strict consent rules, carrier filtering, character limits | Time-critical alerts, short reminders, two-way confirmations |
| WhatsApp Business Platform | Rich media, buttons, two-way conversations, dominant in many markets (for example Nigeria, India, Brazil) | Template approval, message categories and per-message pricing, opt-in requirements | Order and appointment updates, support conversations, considered offers |
| Email | Cheap, long-form, permanent | Lower attention | Education, newsletters, detail |
| Push and in-app | Free, contextual | Requires app and permission | Product nudges |

## WhatsApp pricing and categories (2026)
Since 1 July 2025 Meta charges per delivered template message rather than per conversation. Price depends on the market and category (marketing, utility, authentication). Utility templates sent inside an open 24-hour customer service window are free; marketing templates are always charged. Meta may change rates only on the first day of a quarter. [Confirmed, Meta developer documentation] Check current rate cards before forecasting costs.

## Operating principles
1. **Consent per channel, recorded.** SMS and WhatsApp consent must be explicit and separate from email consent in most markets.
2. **Earn the interruption.** Send only what is time-sensitive, personal or requested.
3. **Classify messages correctly.** Utility (order, account, appointment) and marketing messages follow different rules and prices.
4. **Make opting out easy.** STOP keywords for SMS; clear opt-out for WhatsApp.
5. **Measure incrementality.** Many SMS "conversions" would have happened from email alone.

## Compliance essentials (check local law)
| Market | Key points |
|---|---|
| United States | TCPA consent rules for marketing texts; carrier registration for A2P 10DLC (brand and campaign registration); quiet hours rules in some states; honour STOP |
| United Kingdom | PECR requires prior consent for marketing texts (soft opt-in for existing customers in limited cases); clear opt-out |
| European Union | GDPR and ePrivacy consent; record proof |
| Nigeria | NDPA data protection rules; NCC regulations and do-not-disturb rules for SMS |
| WhatsApp everywhere | Meta's opt-in requirements and Business Messaging Policy; template approval |
This is not legal advice; confirm with counsel for each market.

## When to use, and when not to
Use it when adding SMS or WhatsApp to lifecycle, when costs rise without clear return, when opt-out rates are high, or in markets where WhatsApp leads.

Don't use it for email-only programmes (`lifecycle-email-copy-design`) or for deliverability on email (`email-deliverability`).

## Inputs to ask for, in one message
1. Markets and audiences, and which channels customers use there.
2. Provider and setup (for example Attentive, Postscript, Klaviyo SMS, Twilio, a WhatsApp Business Solution Provider).
3. Consent capture method and records.
4. Current flows, volumes, costs, opt-out and conversion rates.
5. WhatsApp templates and their categories, if used.

## Workflow

### Step 1. Decide channel roles
For each journey moment, choose the channel by urgency, richness and cost. SMS and WhatsApp should add something email can't.

### Step 2. Set up consent
Separate checkboxes or keyword opt-ins, clear wording on what and how often, double opt-in where appropriate, records with source and timestamp.

### Step 3. Register and configure
For US SMS, complete 10DLC brand and campaign registration (or use toll-free verification or short codes). For WhatsApp, verify the business, set display name, and create templates in the right categories.

### Step 4. Design flows
Transactional and utility first (order, delivery, appointments, payment failure), then high-intent marketing (cart abandonment with stock or price urgency, back-in-stock, early access for subscribers who asked).

### Step 5. Write messages
Identify the brand first, keep SMS short, one link, clear opt-out language where required, no misleading urgency. For WhatsApp, use buttons for common replies and route replies to people or support.

### Step 6. Set frequency and quiet hours
Cap marketing texts per week, respect local quiet hours and time zones, and suppress SMS when the same message just went by email and was acted on.

### Step 7. Manage costs
Forecast by message count, market and category. Use utility templates inside the service window where appropriate; avoid sending marketing templates to low-value segments.

### Step 8. Measure
Incremental conversions against holdouts, revenue per message after cost, opt-out rate, reply rate and support deflection.

## Message examples
| Moment | SMS | WhatsApp |
|---|---|---|
| Shipped | "[Brand]: your order is on its way, arriving Thu. Track: [link]" | Utility template with tracking button |
| Payment failed | "[Brand]: your payment didn't go through. Update in 1 min: [link] Reply STOP to opt out" (where marketing rules apply) | Utility template with update button |
| Back in stock | "[Brand]: the [item] you wanted is back. [link]" | Marketing template with image and buy button |
| Appointment | "[Brand]: reminder, your appointment is tomorrow 10:00. Reply C to confirm" | Utility template with confirm and reschedule buttons |

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Same message on email and SMS | Send SMS only if email isn't acted on within a set time |
| WhatsApp template rejected or reclassified | Rewrite to fit the category; don't disguise marketing as utility |
| High opt-out after a campaign | Check frequency, relevance and timing; pause similar sends |
| International numbers | Format in E.164, respect each country's rules and costs |
| Customers reply with questions | Route to support; a conversation is the channel's main advantage |

## Handoffs to related skills
- Consent records: `crm-data-hygiene`
- Journey timing: `customer-journey-mapping`
- Dunning and retention: `retention-churn-prevention`
- Win-back with consent: `win-back-reactivation`
- Holdouts: `lifecycle-experimentation`
- Cost and revenue reporting: `lifecycle-reporting-attribution`

## Worked example
An online fashion retailer in Lagos sent marketing by email and SMS, with high SMS costs and weak results. Customer research showed most buyers preferred WhatsApp. The team moved order updates to WhatsApp utility templates (free inside the service window when customers had messaged recently), added a back-in-stock marketing template for customers who requested alerts, routed replies to customer service and kept SMS only for delivery-day alerts. A holdout showed the back-in-stock template drove incremental sales, messaging costs fell, and support calls about order status dropped.

## Output format
```
# SMS and WhatsApp plan: <business>, <markets>, <date>
## Channel roles by journey moment
## Consent and compliance by market
## Registration and template setup
## Flows and message copy
## Frequency, quiet hours and suppression rules
## Cost forecast by market and category
## Measurement with holdouts
```

## Common mistakes
- Using SMS as a copy of email.
- Consent bundled with email or buried in terms.
- Marketing disguised as utility templates.
- Ignoring quiet hours and time zones.
- Counting attributed revenue without holdouts or costs.

## Questions to ask before you design
- Which messaging apps do customers in each market prefer?
- How is SMS and WhatsApp consent captured and recorded?
- What does each message cost by market and category?

## Self-check before you answer
- Is consent explicit, per channel and recorded?
- Does every message earn the interruption?
- Are templates in the right categories and costs forecast?
- Is impact measured incrementally after cost?

## Official documentation
- WhatsApp Business Platform pricing: https://developers.facebook.com/docs/whatsapp/pricing
- WhatsApp Business Messaging Policy: https://business.whatsapp.com/policy
- CTIA messaging principles and best practices: https://www.ctia.org/
- UK ICO guidance on electronic marketing: https://ico.org.uk/for-organisations/direct-marketing-and-privacy-and-electronic-communications/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/sms-whatsapp-lifecycle/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
