---
name: release-notes
description: >-
  Rewrites raw launch notes into a 7-line narrative newsletter slot for
  company-wide or customer-facing product newsletters. Self-contained, professional
  tone, context built in. Use when writing release notes, ship announcements,
  sprint summaries, or exec-ready launch briefs for a newsletter.
---

# Release Notes — Newsletter Launch Slot

Writes **one launch slot** inside a weekly/monthly newsletter (not the full newsletter). Output: **7 lines** of narrative prose — professional, self-contained, not childish, not engineering-heavy.

## Non-Negotiable Rules

- **7 lines exactly** — one sentence/thought per line; no bullets, labels, arrows, or headers
- **Slot only** — never write newsletter intro, other launches, or footer
- **Self-contained** — reader may skim only this block
- **Never invent** metrics, dollars, percentages, rollout %, or "statistically significant"
- **PRD link required** on line 7 before final output; **ticket link optional**
- **Extract before re-ask** — parse raw notes first; ask only for gaps
- **No qualitative filler** without metrics — user must say **"No impact metrics"** explicitly
- Dollar figures only if user, dashboard, or Snowflake provided them — never extrapolate from %

## Workflow

```
ENTRY → EXTRACT → GATE → WRITE (7 lines) → CHECK → REVISE (optional) → SAVE (optional)
```

---

## ENTRY

**1. Input source**
- Paste raw notes / engineering summary (default)
- Jira fix version or epic key → summarize, then continue
- Draft 7-line block → polish only

**2. Audience** (always ask)

"Audience: **company-wide newsletter** (default) or **customer-facing**?"

Default: company-wide.

**3. Multiple features** (if paste has several ships)

"One 7-line block for the whole paste, or **one block per feature**?"

Default: one block per distinct feature; otherwise one block.

---

## EXTRACT

Before gate, infer from raw notes / Jira:

| Field | Extract |
|-------|---------|
| Feature name | Plain-English ship name |
| Launch / rollout | Date, % live, audience |
| Impact metrics | %, $, counts |
| Ticket | Key + URL (optional) |
| PRD | URL (**required** for final write) |

Tell user: "I found: [list]. I still need: [gaps only]."

**Full gate and data-source rules:** [data-sources.md](data-sources.md)

---

## GATE — Gaps only

Ask **only** what extract did not resolve.

**Launch / rollout** (if missing):
When did this ship, and what % of users is it live to (and which audience)?

**Impact metrics** (if missing):

Do you have measurable outcomes? Share directly, paste a dashboard/WBR export, or point to Snowflake (approved query or your export). If none, reply **"No impact metrics"**.

**PRD** (if missing — required):

I need the **PRD link** before I can finalize. Ticket link is optional.

Do not write until launch/rollout is filled, metrics provided or "No impact metrics" confirmed, and **PRD URL** provided.

---

## WRITE — 7 lines

Internal guide (invisible in output):

| Line | Purpose |
|------|---------|
| 1 | Hook — what shipped |
| 2 | Who benefits |
| 3 | Context built in (surface + brief explanation) |
| 4 | Rollout — when / scale |
| 5 | Impact — metric with context, or **skip** if no metrics |
| 6 | Why it matters |
| 7 | Links: `[TICKET](url) – [PRD](url)` — ticket optional, PRD required |

**If "No impact metrics":** skip line 5 impact content — strengthen lines 3 or 6. No "improves performance" substitutes.

**Early signal:** only if user provided a specific number.

**Audience rules:** [terminology-guide.md](terminology-guide.md)

**Customer-facing:** no Jira links; plain rollout language; customer-safe PRD/help URL.

---

## CHECK

- [ ] 7 lines exactly
- [ ] Gate satisfied (launch, metrics or explicit none, PRD URL)
- [ ] PRD on line 7; ticket only if provided
- [ ] No invented numbers or significance
- [ ] No bullets/arrows/labels
- [ ] Standalone — no cross-references to other newsletter items

---

## REVISE (optional)

"Want it shorter, less jargon, or a pass for customer-facing?"

One revision pass unless user asks again.

---

## SAVE (optional)

`outputs/[feature-slug]-release-note.md`

**Examples:** [examples.md](examples.md)
