# BRD, PRD & Release Notes — AI Instructions

Human-readable summary. Full detail in `.cursor/skills/*/SKILL.md`.

---

## BRD (`@brd`)

**Defines WHAT and WHY** — not HOW. Audience: executives, CTO, business owners.

### How to start

`@brd` or "Help me write a BRD"

- Brainstorming from scratch
- Paste existing notes/doc/brief
- Draft BRD → skip to review

### Rules

- One question per response
- Never invents data, SQL, or session metrics
- **6-page main body** (1 TOC + 5 content)
- **Appendix A: BRD Checklist** — separate, not counted in 6 pages
- No solution language

### Data sources (before Fields 3–5)

Ask which connected tools to use:
1. Snowflake — warehouse metrics
2. FullStory — session replay evidence
3. Conviva — experience analytics
4. Paste or upload
5. Manual only
6. Skip quant

### Interview — 17 fields + FAQ

Problem (1–5) · Market (6–7) · Current state (8) · Outcome (9) · Urgency (10) · Financial (11–12) · Approval (13–17) · FAQs

### After interview

1. GENERATE → 2. REVIEW → 3. EXPORT (6-page body + appendix docx) → 4. PRD handoff (optional)

### Outputs

```
outputs/[project-name]-brd.md
outputs/[project-name]-brd.docx
```

---

## PRD (`@prd`)

**Defines HOW** — solution design for eng/design. Audience: PM, engineering, design.

### How to start

`@prd` or "Help me write a PRD"

1. Brainstorming
2. **Have a BRD** — build PRD from approved BRD
3. Have notes
4. Draft PRD → review

### Rules

- 6-page hard limit
- Never invents SQL or baselines
- One question per response

### After interview

GENERATE → REVIEW → EXPORT → JIRA (optional)

### Outputs

```
outputs/[project-name]-prd.md
outputs/[project-name]-prd.docx
```

---

## Release notes (`@release-notes`)

**One 7-line launch slot** for a product newsletter — not the full newsletter.

### How to start

`@release-notes` or "write release notes for the newsletter"

- Paste raw notes / Jira fix version / draft block

### ENTRY (always ask)

**Audience:** company-wide newsletter (default) or customer-facing

### Rules

- **7 lines exactly** — narrative, no bullets
- Self-contained — reader may skim only this block
- Never invents metrics or dollar figures
- **PRD link required** on line 7; ticket optional
- "No impact metrics" must be explicit from user

### Output

```
outputs/[feature-slug]-release-note.md  (optional)
```

---

## BRD → PRD → Ship flow

1. `@brd` → executive approval
2. `@prd` with BRD as input
3. Ship → `@release-notes` for newsletter slot

## MCP dependencies (optional)

| Tool | BRD | PRD | Release notes |
|------|-----|-----|---------------|
| Snowflake | Impact & evidence | Impact baselines | Impact line |
| FullStory | Session evidence | — | — |
| Conviva | Experience evidence | — | — |
| Atlassian | — | Jira handoff | Jira input / ticket link |
| `python-docx` | Docx export | Docx export | — |
