# PRD Assistant — AI Instructions

Human-readable summary of the `@prd` skill. For full detail, see `.cursor/skills/prd/SKILL.md`.

## How to start

Ask in Agent chat: `@prd` or "Help me write a PRD"

Entry options:
1. Brainstorming — rough idea, guided interview
2. Have a BRD — paste it, build PRD
3. Have notes — paste partial details
4. Have a draft PRD — skip to review

## Rules the agent follows

- One question per response
- Never invents data, SQL, or baselines
- Missing fields show as `[Enter text]`
- 6-page hard limit (1 TOC + 5 content pages)
- Escalates thin answers before moving on

## Interview — 19 fields

| # | Field |
|---|-------|
| 1–2 | Problem statement, goals |
| 3–4 | Persona, hypothesis |
| 5–7 | Impact metrics (data source first) |
| 8–10 | Happy path, friction, edge cases |
| 11–12 | Functional + non-functional requirements |
| 13 | Dependencies (type or Cursor codebase scan) |
| 14–16 | Assumptions, risks, constraints |
| 17–18 | RACXI, release strategy |
| 19 | Stakeholder FAQs |

## Impact analysis (Fields 5–7)

Agent asks data source before metrics:
1. Manual
2. Team NSM reference file (`references/nsm-config.yaml`)
3. Paste or upload (WBR CSV, dashboard export)
4. Snowflake (approved query templates only)
5. Skip quant

Every metric in the PRD includes a **Source** label.

## After interview

1. **GENERATE** — markdown draft from template
2. **REVIEW** — critical audit; ask apply all or changes only
3. **EXPORT** — 6-page docx to `outputs/`
4. **JIRA** (optional) — link, Epic+backlog, or Confluence

## Dependencies you may need

| Tool | For |
|------|-----|
| `python-docx` | Docx export (`pip install -r requirements.txt`) |
| Atlassian MCP | Jira Epic + tickets |
| Snowflake MCP | Impact baselines (optional) |

## Outputs

```
outputs/[project-name]-prd.md
outputs/[project-name]-prd.docx
```
