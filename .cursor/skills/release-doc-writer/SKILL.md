---
name: release-doc-writer
description: >-
  Creates the long-form release doc (Calendar of Product Release Notes template)
  that backs each 7-line newsletter slot. Produces What it Is, Why it Matters,
  Key Benefits, NSMs Impacted, Kudos, and Visuals. Use when creating a release
  one-pager, filling the release doc template, or when @release-notes hands off
  because no doc exists yet.
---

# Release Doc Writer

Creates the **detailed release doc** — the structured one-pager that PM/Eng maintain
in Google Docs. One release = one doc.

The condensed **7-line slot** is a separate artifact from `@release-notes`.

**Template:** [references/release-doc-template.md](references/release-doc-template.md)
**Canonical Google Doc:** https://docs.google.com/document/d/1KP8azye_-j8XeL2ODHBx2v3Mww7thK7BrJoiOz5j1-w/edit

## Non-Negotiable Rules

- **Never invent** metrics, dollars, percentages, dates, owners, or NSM impact
- **Every section present** — match template labels exactly; use `TBD` for unknown content and flag to user
- **PRD link required** before final output
- **Plain-English first** — same voice bar as the newsletter slot
- **Extract before re-asking** — pull from pasted notes, Jira epic, or PRD first
- **Output structure** — must match `references/release-doc-template.md`; only fill placeholders

## Workflow

```
ENTRY → GATHER → WRITE → REVIEW → EXPORT → HANDOFF (optional)
```

---

## ENTRY

Ask: **"Do you already have the release doc, or should I create it?"**

- **Exists** → get the link. Offer gap-check (missing sections, PRD, Visuals). Done unless user wants updates.
- **Create it** → GATHER

---

## GATHER

Extract from raw notes, Jira epic, PRD, or Slack thread. Ask **only for gaps**.

| Field | Notes |
|-------|-------|
| Business unit | Thomas / Xometry US / EMEA / APAC (matches newsletter section) |
| Product Release | Plain-English ship name |
| Release Date | MM/DD/YYYY |
| Product Owner | Name |
| Tech Owner | Name |
| Business Owner | Name |
| PRD Link | URL — **required** |
| What it Is | What shipped, plain English |
| Why it Matters | Problem / cost of status quo |
| Key Benefits | Concrete outcomes; metrics only if provided |
| NSMs Impacted | North Star Metrics affected |
| Kudos | Contributor names |
| Visuals | GIFs, before/after, tables — or TBD |

Tell user: "I have: [extracted]. I still need: [gaps]."

Do not write until PRD and core narrative (What / Why / Benefits) are in hand.

**Section guidance:** [references/release-doc-template.md](references/release-doc-template.md)
**Example:** [examples.md](examples.md)

---

## WRITE

Fill the template verbatim. Section rules:

- **What it Is** — what it does and where it lives; no deploy mechanics
- **Why it Matters** — before-state and cost; figures only if user provided
- **Key Benefits** — business/user outcomes; metrics only if provided
- **NSMs Impacted** — name metrics; don't assume impact direction
- **Kudos** — names as given
- **Visuals** — preserve pasted tables exactly; `TBD` if none yet

---

## REVIEW

Run [review-checklist.md](review-checklist.md). Critically review for solution jargon, thin narrative, unsupported claims.

Ask: **"Apply all suggested changes, or show changes needed only?"**

---

## EXPORT

Produce copy-ready text matching the template. Then:

- User duplicates the canonical Google Doc and pastes content, **or**
- User saves to `outputs/[feature-slug]-release-doc.md`

If Google Drive MCP is available, offer to create the doc — confirm folder and All Staff sharing first; never guess permissions.

---

## HANDOFF

When approved, offer:

> "Ready to draft the 7-line slot for **#pdt-releases**? Use `@release-notes`."

Provide: **doc title** and **doc URL** for reference. No mailto or owner email lead-in.
