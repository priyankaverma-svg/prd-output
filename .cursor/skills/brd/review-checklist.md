# REVIEW — Critical BRD Audit

Run after GENERATE or when user pastes an existing BRD.

Audit **main body** for 6-page limit. Audit **Appendix A** separately for completeness.

## Completeness (17 fields + FAQ)

| Check | 🔴 Must fix if |
|-------|----------------|
| WHO affected | No segment or scale |
| WHAT breaks | Solution language or no failure sequence |
| Measurable outcome | No number and no honest placeholder |
| Evidence | Tier unstated; Tier 4 without validation plan |
| Business impact | No quantified consequence |
| Competitive context | "Maybe" with no N/A reasoning |
| Current state | Repeat of Field 2 only |
| Desired outcome | Feature description not business outcome |
| Urgency | "Important" with no forcing function |
| Financial impact | No number or range |
| Business owner | TBD at generate time |
| FAQs | Fewer than 3 Q&A pairs |

## Data Integrity

| Check | 🔴 Must fix if |
|-------|----------------|
| Source labels | Numbers without Source field |
| Invented data | Agent claims Snowflake/FullStory/Conviva data not pulled |
| Solution language | HOW described anywhere in main body |
| BRD vs PRD boundary | Technical requirements in BRD |

## Page Budget (main body only — 6 pages)

| Check | 🟡 Should fix if |
|-------|------------------|
| Problem section | More than 1 page equivalent |
| Financial table | Verbose Year 1–3 prose |
| FAQs | More than 3 or long answers |
| Total body | Likely exceeds 6 pages |

Appendix A checklist overflow is 🟢 acceptable.

## Appendix A

| Check | Severity |
|-------|----------|
| Checklist missing | 🔴 |
| Checklist in main body as Section 5 | 🔴 — move to Appendix A |
| PRD Initiated not "No" on draft | 🟡 |

## Review Output

```markdown
## BRD Review — [Project Name]

| # | Finding | Severity | Section | Recommendation |
|---|---------|----------|---------|----------------|
| 1 | [finding] | 🔴/🟡/🟢 | [section] | [fix] |

**Summary:** [N] must-fix, [N] should-fix, [N] optional
**Main body pages (est.):** [N] / 6
```

Ask:

"I found [N] recommendations ([X] must-fix, [Y] should-fix, [Z] optional). Do you want me to **apply all changes**, or **show changes needed only**?"
