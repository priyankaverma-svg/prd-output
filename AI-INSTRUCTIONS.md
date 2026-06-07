# BRD & PRD Assistant — AI Instructions

Human-readable summary. Full detail in `.cursor/skills/brd/SKILL.md` and `.cursor/skills/prd/SKILL.md`.

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

## BRD → PRD flow

1. Complete BRD with `@brd`
2. Get executive approval (Appendix A checklist)
3. Start `@prd` with BRD as input
4. Optional Jira Epic + backlog from PRD

## MCP dependencies (optional)

| Tool | BRD | PRD |
|------|-----|-----|
| Snowflake | Impact & evidence | Impact baselines |
| FullStory | Session evidence | — |
| Conviva | Experience evidence | — |
| Atlassian | — | Jira handoff |
| `python-docx` | Docx export | Docx export |
