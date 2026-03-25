---
name: audit-ghana-biz
description: Audit a Greater Accra SME for AI automation opportunities and generate a Business ROI Report.
arguments: business_name_or_url
---

# Skill: /audit-ghana-biz [Business Name/URL]

Analyze a Greater Accra SME's operations and produce a **Business ROI Report** with concrete automation recommendations.

## Invocation

```
/audit-ghana-biz [Business Name or URL]
```

## Process

### Step 1: Research the Business

Search for the business using web search to gather:
- Business name, sector (Hospitality / Logistics / Private Schools), and location in Greater Accra
- Online presence — website, social media, Google Business listing
- Customer reviews mentioning service gaps (slow responses, limited hours, booking friction)
- Current tools visible from their public presence (WhatsApp-only contact, booking forms, etc.)

### Step 2: Identify Automation Gaps

Check for the following pain points:

- **Manual booking / appointment flows** — Are customers required to call, WhatsApp, or walk in to book? Is there an online booking system, or is it all manual?
- **Lack of 24/7 customer support** — Is there evidence of night-shift coverage? Do reviews mention unanswered calls or delayed responses after hours? This is critical for Ghana's "24-Hour Economy" push.
- **Inconsistent digital presence** — Is the business WhatsApp-only with no integrated CRM? Are inquiries scattered across phone, WhatsApp, email, and social media with no central system?

### Step 3: Draft the Business ROI Report

Generate a report with the following sections:

#### Business Summary
- Name, sector, location, size (if available)
- Current digital maturity level (Paper-based / WhatsApp-only / Partially Digital / Integrated)

#### Automation Gaps Found
- Table of identified gaps with severity (High / Medium / Low)

#### ROI Estimates
- **Estimated monthly hours saved** by automating FAQs — Based on sector benchmarks (e.g., a boutique hotel fielding ~20 WhatsApp inquiries/day, 3 min each = 30 hrs/month of staff time on repetitive questions)
- **Revenue potential of a 24/7 AI Voice Agent** for after-hours calls — Estimate missed bookings/orders from after-hours inquiries that go unanswered, and the revenue those represent

#### Top Recommendations (Ranked by ROI)
For each recommendation:
1. **What to automate** — Plain-language description
2. **Recommended solution** — e.g., WhatsApp chatbot, AI voice agent, automated booking pipeline
3. **Expected benefit** — Hours saved, revenue recovered, error reduction
4. **Quick win or long-term project** — Can this ship in days or weeks?

#### Next Steps
- 2-3 concrete actions the business owner can take immediately

### Step 4: Save the Report

Save the completed report to:
```
proposals/[business-name].md
```
Use a slugified version of the business name (lowercase, hyphens, no spaces). Create the `proposals/` directory if it does not exist.

## Output Principles

- Write for a **non-technical business owner** — no jargon without explanation.
- Tie every recommendation to **money saved or revenue gained**.
- Always emphasize the **24-Hour Economy** angle — what keeps working when the owner goes home.
- Be honest — not everything needs AI. If a spreadsheet solves the problem, say so.
- Use conservative estimates for ROI — underpromise, overdeliver.
