---
name: crm-data-hygiene
description: "Audit and fix CRM and marketing data across completeness, validity, accuracy, uniqueness, consistency and timeliness: data flow and systems of record, field governance, channel-specific consent records, deduplication with match and survivorship rules, source fixes in forms and integrations, list hygiene, deliberate enrichment and a monitoring dashboard for HubSpot, Salesforce, Klaviyo and similar tools. Use whenever someone mentions duplicate contacts, messy CRM data, broken personalisation, consent records, list cleaning, data enrichment, CRM migration preparation or fields nobody trusts."
license: CC-BY-4.0
metadata:
  author: Afeez Adebayo
  author_url: https://afeezadebayo.com
  author_linkedin: https://www.linkedin.com/in/afeez-adebayo/
  author_x: https://x.com/za_icon
  source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/crm-data-hygiene/
  category: marketing
  subcategory: crm-lifecycle
  version: "1.0.0"
  created: "2026-10-10"
  updated: "2026-10-10"
---

# CRM Data Hygiene and Enrichment

Every lifecycle message depends on data: the right event triggering the right flow, a first name that is actually a name, a consent flag that reflects what the person agreed to, a company record that isn't one of three duplicates. Bad data shows up as broken personalisation ("Hi FIRSTNAME"), customers in the wrong journey, sales reps calling people who already bought, reports nobody trusts and, worst of all, messages sent to people who never agreed to receive them.

This skill audits CRM and marketing data, fixes it at the source, and sets rules so it stays clean.

## Operating principles
1. **Fix at the source.** Cleaning the CRM while forms and integrations keep creating bad records is a treadmill.
2. **One owner per field.** Every important field has a system of record and a person responsible.
3. **Consent data is the most important data.** It must record channel, source, wording and time.
4. **Merge with rules, not guesses.** Define which record wins and which values survive before deduplicating.
5. **Enrich only what you use.** Every extra field costs money, privacy risk and maintenance.

## Data quality dimensions
| Dimension | Question | Example problem |
|---|---|---|
| Completeness | Are required fields filled? | 40% of contacts missing country, so regional rules can't apply |
| Validity | Do values follow the format? | Phone numbers without country codes |
| Accuracy | Do values match reality? | Job titles years out of date |
| Uniqueness | One record per person or company? | Same customer as three contacts from three forms |
| Consistency | Same value across systems? | Plan tier differs between billing and CRM |
| Timeliness | Is data fresh enough for its use? | Purchase events arrive a day late, so flows fire after the customer has moved on |

## When to use, and when not to
Use it when personalisation breaks, duplicates frustrate sales, flows trigger wrongly, before migrations, before enrichment purchases and when consent records are unclear.

Don't use it to design segments (`lifecycle-segmentation`) or to score leads (`lead-scoring-routing`), though both depend on clean data.

## Inputs to ask for, in one message
1. Systems and how data flows between them: CRM, messaging platform, billing, product, CDP or warehouse, forms, integrations.
2. A field list with definitions, fill rates and which system writes each field.
3. A sample export of 500 to 1,000 records (with personal data minimised or masked).
4. Duplicate counts and the current deduplication method.
5. Consent fields and how they are captured.
6. Known pain points from sales, support and marketing.

## Workflow

### Step 1. Map the data flow
Draw every source that creates or updates records and every system that reads them. Mark the system of record for each key field.

### Step 2. Profile the data
For key fields: fill rate, distinct values, invalid formats, outliers. Count duplicates by email, phone and company domain.

### Step 3. Audit consent
Check each marketing contact has a channel-specific consent status, source, timestamp and, ideally, the wording shown. Identify contacts with unknown consent; they shouldn't receive marketing until resolved.

### Step 4. Define standards
Formats (country codes, ISO country names, lowercase emails), picklists instead of free text, required fields per record type, naming for properties.

### Step 5. Deduplicate with rules
Match rules (exact email; normalised phone; company domain plus name), survivorship rules (most recent non-empty value, or source priority), and a review queue for uncertain matches. Back up before merging.

### Step 6. Fix sources
Form validation, required fields, picklists, integration mappings, and blocking role-based or disposable addresses where appropriate.

### Step 7. Enrich deliberately
For B2B, enrich firmographics (industry, size, location) used by scoring and routing. Prefer progressive profiling (asking for one more detail at a time) over buying data where possible. Check vendors' data sources and compliance.

### Step 8. Monitor
A weekly data quality dashboard: duplicates created, invalid emails, missing consent, failed syncs.

## Email list hygiene
- Remove hard bounces immediately; suppress repeated soft bounces.
- Suppress complainers and unsubscribes across every sending tool.
- Verify addresses at capture (real-time validation) rather than buying cleaning later.
- Never buy or rent lists; they damage deliverability and often break consent law.
- Watch for spam traps: they appear in old, purchased or scraped lists.

## Field governance template
```
| Field | Definition | Format | System of record | Writes from | Required? | Owner | Used by |
| lifecycle_stage | Current stage per journey map | Picklist | Messaging platform | Events | Yes | Lifecycle lead | Journeys, reports |
```

## Minimum consent record
| Field | Example | Why |
|---|---|---|
| Channel | Email, SMS, WhatsApp, push | Consent is channel-specific in many markets |
| Status | Subscribed, unsubscribed, pending double opt-in | Drives sending eligibility |
| Source | Checkout checkbox, footer form, event badge scan | Shows how consent was given |
| Timestamp and timezone | 2026-09-14 10:32 UTC | Evidence and audit trail |
| Wording version | Form text v3 | Proves what the person agreed to |
| IP or device (where lawful) | Captured at form submit | Supports evidence |
| Market or jurisdiction | UK, EU, US state | Applies the right rules |

## Deduplication rules example
1. **Match:** exact lowercase email; then normalised phone (E.164); then company domain plus first and last name for B2B.
2. **Survivor record:** the oldest record with purchase history, so order links stay intact.
3. **Field survivorship:** most recent non-empty value for contact details; billing system wins for plan and revenue fields; never overwrite consent with an older value.
4. **Review queue:** fuzzy matches below a confidence threshold go to a person.
5. **Log:** keep a record of every merge with both original IDs.

## Data quality dashboard
| Metric | Target | Alert when |
|---|---|---|
| New duplicates per week | Near zero | Rises above usual level |
| Contacts missing consent source | 0 for new records | Any new record without source |
| Invalid email rate at capture | Low | Jumps after a form change |
| Failed integration syncs | 0 | Any failure for more than an hour |
| Key field fill rate (country, lifecycle stage) | High | Drops after a release |

## Progressive profiling
Ask for one extra detail at each natural moment instead of a long form: role at sign-up, company size at trial start, use case in onboarding, preferences after first purchase. Data collected this way is more accurate, and people understand why it's asked.

## Edge cases and judgement calls
| Situation | What to do |
|---|---|
| Same person, personal and work emails | Keep separate if consent and context differ; link if your CRM supports it |
| B2B contact changes company | Close the old association, keep history, create a new link |
| Consent unknown for old contacts | Exclude from marketing; run a compliant re-permission campaign where law allows |
| Merging thousands of duplicates | Test rules on a sample, back up, run in batches, check reports afterwards |
| Enrichment vendor claims high accuracy | Test on records you can verify before buying at scale |

## Handoffs to related skills
- Segments built on the data: `lifecycle-segmentation`
- Lead scoring and routing: `lead-scoring-routing`
- List quality and bounces: `email-deliverability`
- Event definitions: `customer-journey-mapping`
- Reporting accuracy: `lifecycle-reporting-attribution`

## Worked example
A B2B SaaS company had 210,000 HubSpot contacts and sales complained about duplicates and wrong owners. Profiling showed 18% duplicates (mostly from webinar imports and a broken form integration), job titles as free text with 14,000 distinct values, and 31% of contacts with no recorded consent source. The team fixed the integration, added form validation, mapped job titles to a nine-option role picklist, merged duplicates with domain-based rules after a sample review, and excluded unknown-consent contacts from marketing until a re-permission campaign. Lead routing errors dropped sharply, and personalised campaigns stopped producing blank fields.

## Output format
```
# CRM data hygiene review: <business>, <date>
## Data flow map and systems of record
## Quality profile by field (fill, validity, duplicates)
## Consent audit
## Standards and governance table
## Deduplication rules and plan
## Source fixes
## Monitoring dashboard
```

## Common mistakes
- Cleaning data while sources keep creating new problems.
- Merging without survivorship rules or backups.
- Free-text fields for values used in segmentation.
- Unknown consent treated as consent.
- Buying enrichment data before defining what it's for.

## Questions to ask before you recommend changes
- Which system is the source of truth for each key field?
- Which fields actually drive segmentation, routing or reports?
- What consent records exist, and in which markets?

## Self-check before you answer
- Did I map data flows and owners before cleaning?
- Is consent audited per channel with source and time?
- Are deduplication rules defined and tested?
- Are source fixes included so problems don't return?

## Official documentation and guidance
- UK ICO guidance on direct marketing and consent: https://ico.org.uk/for-organisations/direct-marketing-and-privacy-and-electronic-communications/
- European Data Protection Board guidelines on consent: https://www.edpb.europa.eu/
- HubSpot knowledge base, deduplication: https://knowledge.hubspot.com/

---
Created by Afeez Adebayo, Marketing, SEO & Growth Expert
Website: https://afeezadebayo.com
LinkedIn: https://www.linkedin.com/in/afeez-adebayo/
X: https://x.com/za_icon
Source: https://afeezadebayo.com/skills-md/marketing/crm-lifecycle/crm-data-hygiene/

Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). You may copy, share and adapt this skill, including for commercial use, as long as you credit Afeez Adebayo and link to the source URL above. Keep this notice in any copy or adapted version.
