---
name: release-newsletter-consolidator
description: >-
  Builds the Xometry Product Releases newsletter for Central Communications by
  consolidating release notes posted in #pdt-releases over a chosen date range.
  Handles reminder nudges, buckets releases by business unit, assembles the
  fixed newsletter template, and runs editorial checks — stopping at a
  ready-to-send draft for executive leadership. Use when building the product
  newsletter, consolidating releases, or pulling #pdt-releases for a date window.
---

# Release Newsletter Consolidator

**Audience:** Central Communications (release SPOC).

Reduces manual load of release management checkpoints **1–3**:

1. **Remind** — friendly nudge to PMs in **#pdt-operations**
2. **Consolidate** — read **#pdt-releases** over a date range, bucket by business unit
3. **Format + editorial** — assemble the newsletter template, run checks, hand off draft

**Never performs checkpoint 4 (Send).** Final output is a ready-to-paste draft.
Central Communications sends to executive leadership.

---

## Modes

Ask which step the user is on if it isn't obvious:

- **Remind** → post nudge to #pdt-operations (see Reminder)
- **Consolidate + Format** → date range → read → bucket → assemble → check

Default to Consolidate + Format if the user gives a date range or says "build the newsletter."

---

## Routing tag contract

Every note in **#pdt-releases** should open with a routing tag on line 1 (added by PM via `@release-notes`):

`[<BUSINESS UNIT> · <SECTION>]`

| Tag | Newsletter section |
|-----|-------------------|
| `[Thomas]` | 🔍 Thomas |
| `[US · Buyer Experience]` | 🛒 Buyer Experience |
| `[US · Marketing]` | Marketing |
| `[US · Sales]` | 📈 Sales |
| `[US · Pricing & Manufacturability]` | ⚙️ Pricing & Manufacturability |
| `[US · Partner Experience]` | 🤝 Partner Experience |
| `[US · Post-Order]` | 📦 Post-Order |
| `[US · Financial Systems]` | 📊 Financial Systems |
| `[US · Technology Services]` | 💻 Technology Services |
| `[EMEA]` | 🇪🇺 Xometry EMEA |
| `[APAC]` | 🌐 Xometry APAC |

**Untagged or mis-tagged notes:** do NOT silently drop. Infer the most likely bucket, place it there, and flag in "⚠️ Needs review" at the end. Never invent a bucket not in the table.

---

## Step 1 — Date range

Get the release window before reading anything.

Ask: "What's the release window? Give me **From (MM/DD/YYYY)** and **To (MM/DD/YYYY)**."

From the window, derive header dates:
- **Window label** → `Month DD - Month DD` (e.g. `May 27 - June 9`)
- **Content Due** and **To be sent on** → from previous issue cadence if known; otherwise ask. Never guess send dates.

---

## Step 2 — Read #pdt-releases

Read messages in **#pdt-releases** between From and To (inclusive). Include thread replies — use the latest version.

For each release capture: routing tag, 7-line slot, PRD/ticket links.

If Slack MCP is unavailable, ask user to paste raw posts; continue from paste.

---

## Step 3 — Bucket

Sort every release into its section using the routing tag table. Preserve PM's 7-line prose as-is — consolidate, don't rewrite slots.

Light touch only: fix obvious typos, normalize link format, trim stray labels. Flag slots needing rework rather than rewriting.

Order within a section by ship date (earliest first); if dates missing, keep channel order.

---

## Step 4 — Assemble

Fill [references/newsletter-template.md](references/newsletter-template.md) exactly. Keep every business header even if empty (`* (no releases this window)` — never delete a header). Preserve emojis, links, and section order.

- Title: `🎯 Product Releases | {window label}`
- `Content Due:` and `To be sent on:` from Step 1
- **Executive Summary:** start with `Hello again Xometry!` then leave `…` for the human, OR draft 2–3 sentences only if user asks. Never fabricate an exec summary.

---

## Step 5 — Editorial + format checks

- [ ] Every header from template present and in order
- [ ] Every release under exactly one section
- [ ] Each slot intact 7-line prose — no stray bullets, arrows, or labels
- [ ] No invented metrics, dates, or links introduced during consolidation
- [ ] PRD link on each slot's last line (flag missing — don't invent)
- [ ] Header dates (window, due, send) all filled
- [ ] "⚠️ Needs review" list if any note was inferred, untagged, or missing PRD

---

## Step 6 — Handoff (not send)

Deliver assembled newsletter as copy-ready block. State plainly:

> Draft is ready. Executive summary and final send to leadership are yours — I don't send the newsletter.

Surface "⚠️ Needs review" list. Offer one editorial revision pass.

Save optional: `outputs/product-releases-{window-slug}.md`

---

## Reminder (checkpoint 1)

When asked to nudge, draft for **#pdt-operations**:

> 👋 Friendly nudge — release notes for the next Product Releases newsletter are due **{Content Due date}**. Drop your 7-line slot in **#pdt-releases** with your section tag on line 1 (e.g. `[US · Sales]`). Need the format? Use `@release-notes`. Thanks all!

Confirm due date before posting. Draft for review unless user says send directly.
