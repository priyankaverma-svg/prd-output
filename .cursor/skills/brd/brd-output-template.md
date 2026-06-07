# BRD Output Template

**Main body hard limit:** TOC page + 5 content pages = **6 pages TOTAL** when printed.
**Appendix A does not count** toward the 6-page limit.

## Page Budget (main body only)

| Section | Max space |
|---------|-----------|
| Title + TOC | Page 1 only |
| 1. Problem Statement | ~1 page |
| 2. Market & Opportunity Validation | ~3/4 page |
| 3. Current State vs Desired State | ~3/4 page |
| 4. Business Impact & Justification | ~1 page |
| 5. FAQs | ~1/4 page |

## Writing Rules

- Outcome-led, no jargon, no solution language
- Sections 2–4: bullets over prose where possible
- Evidence table: max 4 rows
- Financial table: 1 line per row (Year 1–3 compact)
- Max 3 FAQs, 1 sentence each
- Chart placeholders: 1 line only
- Every number must have a **Source** label

## BRD Structure

---

# [Project Name] — Business Requirements Document

| Project Name | [from context] |
|---|---|
| Status | In Progress |
| Business Owner | [Field 15] |
| Date | [today's date] |
| OKR Link | [Field 13] |
| Target Timeline | [Field 14] |
| Teams Involved | [Field 16] |
| Budget Requested | [Field 17 — "None requested" if none, never blank] |

## Table of Contents

| Section | Page |
|---------|------|
| 1. Problem Statement | 2 |
| 2. Market & Opportunity Validation | 3 |
| 3. Current State vs Desired State | 4 |
| 4. Business Impact & Justification | 5 |
| 5. FAQs | 6 |
| Appendix A: BRD Checklist | A-1 |

---

## 1. Problem Statement

**1.1 Problem Definition** [Fields 1, 2, 3]
[WHO] experience [WHAT] when [context], resulting in [MEASURABLE OUTCOME].

If no number: `[Enter text — tip: pull volume data from analytics or ask data team for 30-day export.]`

| Source | [Snowflake / FullStory / Conviva / manual / user paste — never omit if numbers present] |

**1.2 Evidence** [Field 4]
| Evidence Tier | [Tier 1/2/3/4 + one-line description] |
|---|---|
| Source | [named source + tool if applicable] |
| Key Findings | [specific data, quotes, or findings] |
| Gaps to Close | [what data is still missing] |

If Tier 4: | Validation Plan | [who will pull what data by when] |

**1.3 Impact & Scope** [Fields 1, 3, 5, 13, 14, 16]
| Affected KPI(s) | [Field 5] |
|---|---|
| OKR Link | [Field 13] |
| Estimated Accounts Affected | [scale from Field 1] |
| Estimated Timeline | [Field 14] |
| Cross-Team Dependencies | [Field 16] |

---

## 2. Market & Opportunity Validation

**2.1 Competitive Landscape** [Field 6]
Narrative: competitors, gap, acquisition/retention risk. Max 2 sentences.
If N/A: "Not applicable — internal capability without direct competitive equivalent."

**2.2 Market Growth & Timing** [Fields 7, 10]
Why solving now compounds returns. Max 3 bullets.

---

## 3. Current State vs Desired State

**3.1 Current State** [Field 8]
Narrative: what breaks, operational impact, workaround cost. Max 5 bullets.
| Source | [FullStory session / ticket / manual] |

**3.2 Desired Business Outcome** [Field 9]
[Metric] from [current] to [target] within [timeframe]. Outcome only — no solution language.

**3.3 Why Now** [Field 10]
- [Driver]: [user's explanation] — max 3 bullets

---

## 4. Business Impact & Justification

**4.1 Financial Category** [Field 12]
[Categories]

**4.2 Financial Metrics** [Field 11]
| Revenue Impact | [number + reasoning + source] |
|---|---|
| Expected ROI | [target % and timeframe] |
| Gross Margin Impact | [Field 11] |
| Year 1–3 Projection | [compact — one line each or range] |

If rows are [Enter text]: "Action required: complete financial analysis with Data/Finance before sign-off."

---

## 5. FAQs [Field FAQ]

**Q: [question]**
A: [answer — executive tone, 1 sentence]

**Q: [question]**
A: [answer]

**Q: [question]**
A: [answer]

*Living document. Update evidence and projections as analysis completes. See companion PRD for solution design.*

---

## Appendix A: BRD Checklist

*Does not count toward 6-page main body limit.*

| Item | Status | Notes |
|------|--------|-------|
| Market & Opportunity Validated | [Yes / Partial / No] | [rationale] |
| Problem Validated with Evidence | [Tier X] | [source name] |
| Financial Case Completed | [Yes / Pending] | [what's needed] |
| Strategic Alignment Confirmed | [Yes / Pending] | [OKR link] |
| High-Level Feasibility Assessed | [Yes / Not started] | |
| Stakeholder Approval | Pending | |
| PRD Initiated | No | To follow BRD approval |
