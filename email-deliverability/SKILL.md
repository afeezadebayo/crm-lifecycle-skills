---
name: email-deliverability
description: "Get email into the inbox under the 2026 rules from Google, Yahoo and Microsoft: SPF, DKIM and aligned DMARC with a staged rollout, RFC 8058 one-click unsubscribe, spam complaint rates below 0.1% and never 0.3%, list quality and sunset policies, separate transactional and marketing streams, domain and IP warming, Postmaster Tools monitoring and diagnosis of sudden drops. Use whenever someone mentions emails going to spam, deliverability, open rates dropping, Gmail or Outlook bulk sender rules, DMARC, SPF, DKIM, one-click unsubscribe, spam complaints, domain warm-up or switching email platforms."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/email-deliverability/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# Email Deliverability and Inbox Placement

An email that lands in spam or gets rejected might as well not exist. Since 2024 the largest mailbox providers have turned long-standing best practices into requirements: Google and Yahoo announced bulk sender rules in October 2023 and began enforcing them in 2024, Microsoft followed for Outlook.com with enforcement from May 2025, and Gmail stepped up enforcement against non-compliant traffic from November 2025. Senders that ignore them see mail filtered or rejected outright.

This skill audits authentication, list quality, complaint rates, sending behaviour and content, fixes what blocks the inbox, and sets up monitoring so problems are caught before revenue drops.

## The 2026 baseline (bulk senders)
| Requirement | Google | Yahoo | Microsoft (Outlook.com) | Label |
|---|---|---|---|---|
| SPF and DKIM | Required | Required | Required | Confirmed |
| DMARC (at least p=none), aligned with From domain | Required | Required | Required | Confirmed |
| One-click unsubscribe (RFC 8058 headers) for marketing mail | Required | Required | Expected for high-volume senders | Confirmed |
| Process unsubscribes within 2 days | Required | Required | Expected | Confirmed |
| Spam complaint rate | Keep below 0.1%; never reach 0.3% | Keep below 0.3% | Low complaints expected | Confirmed (thresholds published by Google and Yahoo) |
| Valid forward and reverse DNS, TLS | Required | Required | Expected | Confirmed |

Google defines bulk senders as those sending about 5,000 or more messages a day to personal Gmail accounts; once classed as a bulk sender, the status is permanent. Microsoft rejects non-compliant mail from high-volume senders. Rules evolve, so check each provider's current guidance before an audit.

## Operating principles
1. **Authentication is the floor, not the goal.** Passing SPF, DKIM and DMARC lets you in the door; engagement decides where you land.
2. **Complaints matter more than almost anything.** Mail people don't want gets reported, and reports drive filtering.
3. **Send to people who engage.** Sunset inactive addresses; never buy lists.
4. **Change slowly.** New domains, IPs and big volume jumps need warming.
5. **Monitor first-party data.** Google Postmaster Tools, Microsoft SNDS and your platform's bounce and complaint data beat any seed test.

## When to use, and when not to
Use it when open or click rates suddenly fall, when mail lands in spam or bounces, before switching platforms or domains, when starting a high-volume programme, and as a quarterly health check.

Don't use it to improve message copy alone (`lifecycle-email-copy-design`), though content can contribute to complaints.

## Inputs to ask for, in one message
1. Sending domains and subdomains, platforms and dedicated or shared IPs.
2. DNS records: SPF, DKIM selectors, DMARC record and reports if available.
3. Google Postmaster Tools data (spam rate, domain and IP reputation, authentication), Microsoft SNDS if relevant.
4. Bounce, complaint and unsubscribe rates by campaign and stream for 90 days.
5. List sources, sign-up method (single or double opt-in) and sunset policy.
6. Volume patterns and any recent changes.

## Workflow

### Step 1. Check authentication
SPF includes every sending service and stays within the 10-DNS-lookup limit; DKIM signs with the sending domain (not only the platform's domain); DMARC exists and aligns with the visible From domain. Read DMARC aggregate reports to find unknown senders using your domain.

### Step 2. Check one-click unsubscribe
Marketing messages carry `List-Unsubscribe` with an HTTPS URL and `List-Unsubscribe-Post: List-Unsubscribe=One-Click`, both covered by the DKIM signature, plus a visible unsubscribe link in the body. Unsubscribes must take effect within two days.

### Step 3. Read reputation and complaints
In Postmaster Tools, check spam rate trends, domain reputation and delivery errors. Find which campaigns or streams drive complaints.

### Step 4. Review list quality
Sources, opt-in method, age of addresses, bounce rate, inactive share. Remove hard bounces; suppress long-inactive addresses after a re-permission attempt.

### Step 5. Separate mail streams
Use different subdomains (and IPs, if dedicated) for transactional and marketing mail, so a marketing problem doesn't block password resets and receipts.

### Step 6. Review sending behaviour
Consistent volume and timing; gradual ramps for new domains or IPs; no sudden blasts to old segments.

### Step 7. Review content
Clear sender name, honest subject lines, a recognisable brand, a plain way to unsubscribe, reasonable image-to-text balance and working links on reputable domains. Content rarely causes problems alone, but misleading messages drive complaints.

### Step 8. Monitor and alert
Weekly checks of spam rate, bounces and reputation; alerts when spam rate approaches 0.1%.

## DMARC rollout
| Stage | Policy | Goal |
|---|---|---|
| 1 | p=none with reporting (rua) | See every service sending as your domain |
| 2 | Fix alignment for legitimate senders | All real mail passes |
| 3 | p=quarantine (start with pct below 100 if needed) | Protect against spoofing with low risk |
| 4 | p=reject | Full protection |
Moving to enforcement also supports BIMI, which can show your logo in some inboxes once you have a verified mark certificate.

## Warming a new domain or IP
- Start with your most engaged recipients only.
- Increase volume gradually over two to six weeks, depending on size.
- Keep complaint and bounce rates low at every step; pause increases if they rise.
- Don't move all traffic to a new domain on one day.

## Diagnosing a sudden drop
| Symptom | Likely cause | First check |
|---|---|---|
| Gmail opens and clicks fall, others steady | Gmail reputation or spam rate | Postmaster Tools spam rate and reputation |
| Bounces with 5.7.x codes from Outlook | Microsoft requirements not met | Authentication, unsubscribe headers |
| Everything falls after a platform switch | New IPs or domain not warmed, DKIM not set | DNS records, warm-up plan |
| Spike in complaints after one campaign | Unexpected content, old segment or frequency jump | Audience and send history |
| Gradual decline over months | Growing inactive share | Engagement tiers and sunset policy |

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Small sender under bulk thresholds | Still authenticate and keep complaints low; the same filters apply |
| B2B mail to corporate servers | Check Microsoft 365 and gateway filtering; consider content and link reputation |
| Cold outreach | Separate domain, strict volume limits, legal basis checked per market; never mix with customer mail |
| Shared IP on an ESP | Your domain reputation still matters most; follow the ESP's guidance |
| Seed tests disagree with reality | Trust Postmaster data and real engagement over seed inbox placement |

## Handoffs to related skills
- Engagement tiers and sunset: `lifecycle-segmentation`
- List and consent hygiene: `crm-data-hygiene`
- Win-back sending safety: `win-back-reactivation`
- Message content: `lifecycle-email-copy-design`
- Overall programme: `lifecycle-marketing-audit`

## Worked example
An online retailer saw Gmail click rates halve over a month. Postmaster Tools showed spam rate climbing to 0.28% and domain reputation falling to low. The cause: a new "last chance" campaign sent daily to the whole list, including subscribers inactive for over a year. DMARC was also missing, and one-click unsubscribe headers weren't DKIM-signed. The fix: stop daily sends, mail only engaged tiers for three weeks, add DMARC at p=none then quarantine, fix header signing and run re-permission for the inactive group. Spam rate fell below 0.1% within a month and reputation recovered to high.

## Output format
```
# Deliverability review: <sender>, <date>
## Authentication (SPF, DKIM, DMARC, alignment) status
## One-click unsubscribe check
## Reputation and complaints (Postmaster, SNDS, platform data)
## List quality and sunset policy
## Stream separation and sending patterns
## Findings and fixes (priority, owner)
## Monitoring and alert thresholds
```

## Common mistakes
- Treating authentication as the whole job.
- Mailing everyone on the list regardless of engagement.
- Buying or renting lists.
- Sharing one domain for transactional and marketing mail.
- Big volume jumps after a quiet period or platform move.

## Questions to ask before you recommend changes
- Which domains and services send as the brand?
- What does Postmaster Tools show for spam rate and reputation?
- How are inactive subscribers handled?

## Self-check before you answer
- Are SPF, DKIM and DMARC aligned for every sender?
- Are one-click unsubscribe headers correct and signed?
- Is spam rate monitored against Google's thresholds?
- Is there a sunset policy and stream separation?

## Official documentation
- Gmail email sender guidelines: https://support.google.com/a/answer/81126
- Gmail sender guidelines FAQ: https://support.google.com/a/answer/14229414
- Yahoo sender best practices: https://senders.yahooinc.com/best-practices/
- Google Postmaster Tools: https://postmaster.google.com/
- RFC 8058 one-click unsubscribe: https://www.rfc-editor.org/rfc/rfc8058
- DMARC.org: https://dmarc.org/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/email-deliverability/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
