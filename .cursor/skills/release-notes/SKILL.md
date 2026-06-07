---
name: release-notes
description: >-
  Rewrites raw launch notes into a 7-line narrative newsletter slot for
  company-wide or customer-facing product newsletters. Checks for release doc
  first (hands off to @release-doc-writer if missing). Prompts to send to
  #pdt-releases when ready. Use when writing release notes, ship announcements,
  sprint summaries, or exec-ready launch briefs.
---

# Release Notes — Newsletter Launch Slot

Writes **one launch slot** for the product newsletter (not the full newsletter).
PM/Eng post approved slots to **#pdt-releases**; Central Communications consolidates
them into the exec-facing newsletter via `@release-newsletter-consolidator`.

Output: **7 lines** of narrative prose — professional, self-contained, not childish,
not engineering-heavy.

## Non-Negotiable Rules

- **7 lines exactly** — one sentence/thought per line; no bullets, labels, arrows, or headers
- **Slot only** — never write newsletter intro, other launches, or footer
- **Self-contained** — reader may skim only this block
- **Never invent** metrics, dollars, percentages, rollout %, or "statistically significant"
- **PRD link required** on line 7 before final output; ticket link optional
- **Release doc required** — ask first; hand off to `@release-doc-writer` if not prepared
- **Extract before re-ask** — parse raw notes / release doc first; ask only for gaps
- **No qualitative filler** without metrics — user must say **"No impact metrics"** explicitly
- **No mailto** — no owner email lead-in in the slot
- Dollar figures only if user, dashboard, or Snowflake provided them — never extrapolate from %

## Workflow

```
ENTRY → RELEASE DOC CHECK → EXTRACT → GATE → WRITE (7 lines) → CHECK → REVISE → CHANNEL PROMPT
```

---

## ENTRY

**1. Audience** (always ask)

"Audience: **company-wide newsletter** (default) or **customer-facing**?"

Default: company-wide.

**2. Input source**
- Paste raw notes / engineering summary (default)
- Release doc link → read and extract
- Jira fix version or epic key → summarize, then continue
- Draft 7-line block → polish only

**3. Multiple features** (if paste has several ships)

"One 7-line block for the whole paste, or **one block per feature**?"

Default: one block per distinct feature.

---

## RELEASE DOC CHECK (always ask before GATE)

> **"Do you already have the release doc prepared? Paste the link. If not, I'll hand you to `@release-doc-writer` first."**

- **Has doc** → extract fields from doc + any pasted notes → continue to EXTRACT
- **No doc** → stop slot work. Tell user to run `@release-doc-writer`, then return here.

---

## EXTRACT

Before gate, infer from release doc / raw notes / Jira:

| Field | Extract |
|-------|---------|
| Feature name | Plain-English ship name |
| Launch / rollout | Date, % live, audience |
| Impact metrics | %, $, counts |
| Ticket | Key + URL (optional) |
| PRD | URL (**required** for final write) |
| Release doc | Title + URL (from doc check) |

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

**Newsletter section tag** (if missing — required for #pdt-releases):
Which routing tag? Pick one: `[Thomas]` · `[US · Buyer Experience]` · `[US · Marketing]` · `[US · Sales]` · `[US · Pricing & Manufacturability]` · `[US · Partner Experience]` · `[US · Post-Order]` · `[US · Financial Systems]` · `[US · Technology Services]` · `[EMEA]` · `[APAC]`

Never guess the tag — Central Communications sorts by it.

Do not write until launch/rollout is filled, metrics provided or "No impact metrics" confirmed, PRD URL provided, and section tag confirmed.

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

**Customer-facing:** no Jira links; plain rollout language; customer-safe PRD/help URL. Do not prompt to post to #pdt-releases without confirming — that channel is internal.

---

## CHECK

- [ ] 7 lines exactly
- [ ] Release doc confirmed (link on file)
- [ ] Gate satisfied (launch, metrics or explicit none, PRD URL, section tag)
- [ ] PRD on line 7; ticket only if provided
- [ ] No invented numbers or significance
- [ ] No bullets/arrows/labels
- [ ] No mailto or owner email lead-in
- [ ] Standalone — no cross-references to other newsletter items

---

## REVISE (optional)

"Want it shorter, less jargon, or a pass for customer-facing?"

One revision pass unless user asks again.

---

## CHANNEL PROMPT

After the slot is approved, ask:

> **"Ready to send this release to #pdt-releases?"**
> I can draft it in the channel for you to review, or you can copy and post yourself.

**Posted shape** (routing tag is NOT one of the 7 lines):

```
[{section tag}]
<line 1>
<line 2>
...
<line 7>
```

- **Draft in channel for review** — default; use Slack MCP if connected
- **Post directly** — only if user explicitly says so
- **Copy yourself** — give copy-ready text with tag on line 1

Never auto-post without asking. Never post customer-facing slots to #pdt-releases without confirming.

---

## SAVE (optional)

`outputs/[feature-slug]-release-note.md`

**Examples:** [examples.md](examples.md)
