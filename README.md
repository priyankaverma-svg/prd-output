# BRD, PRD & Release Notes Assistant

Cursor skills for product and business teams: BRD/PRD interviews, 6-page docx export, newsletter launch briefs, and BRD → PRD handoff.

## For teammates — get started in 2 minutes

1. **Clone this repo**
   ```bash
   git clone https://github.com/priyankaverma-svg/prd-output.git
   cd prd-output
   ```

2. **Install docx dependency**
   ```bash
   pip install -r requirements.txt
   ```

3. **Open the folder in Cursor** (File → Open Folder → select `prd-output`)

4. **Run a skill** in Agent chat:
   - `@brd` — Business Requirements Document (WHAT & WHY)
   - `@prd` — Product Requirements Document (HOW)
   - `@release-notes` — 7-line newsletter launch slot

5. **BRD/PRD:** one question at a time → review → 6-page docx → optional handoff.

6. **Release notes:** paste raw notes → 7-line newsletter slot (company-wide or customer-facing).

7. **Connect MCP tools** (optional, per person): Snowflake, FullStory, Conviva, Atlassian.

## What's in this repo

| Path | Purpose |
|------|---------|
| `.cursor/skills/brd/` | BRD assistant — 17 fields + FAQ |
| `.cursor/skills/prd/` | PRD assistant — 19 fields |
| `.cursor/skills/prd-codebase-scan/` | Codebase dependency scan (PRD Field 13) |
| `.cursor/skills/release-notes/` | 7-line newsletter launch brief |
| `AI-INSTRUCTIONS.md` | Human-readable workflow summary |
| `outputs/` | Generated BRD/PRD/release-note files |
| `requirements.txt` | Python deps for docx export |

## BRD workflow

```
ENTRY → DATA SOURCES → INTERVIEW (17 + FAQ) → GENERATE → REVIEW → EXPORT → PRD (optional)
```

- **DATA SOURCES**: Snowflake, FullStory, Conviva, paste/upload, or manual
- **6-page main body** (appendix excluded)
- **Appendix A**: BRD Checklist (not counted toward page limit)
- **REVIEW**: Apply all changes or show changes needed only
- **PRD handoff**: `@prd` with BRD as input after approval

## PRD workflow

```
ENTRY → INTERVIEW (19 fields) → GENERATE → REVIEW → EXPORT → JIRA (optional)
```

- Accepts approved BRD as ENTRY option 2
- Snowflake / WBR / paste for impact metrics (Fields 5–7)
- 6-page docx + optional Jira Epic + backlog

## Release notes workflow

```
ENTRY → EXTRACT → GATE → WRITE (7 lines) → CHECK → REVISE (optional)
```

- **One slot** in a weekly/monthly newsletter (not the full newsletter)
- **7 lines** narrative — professional, self-contained, context built in
- **Audience:** company-wide (default) or customer-facing
- **PRD link required** on line 7; ticket optional
- Optional Snowflake / Jira for impact data

## Team setup — analytics config

**BRD** (Snowflake / FullStory / Conviva):
```bash
cp .cursor/skills/brd/references/analytics-config.example.yaml \
   .cursor/skills/brd/references/analytics-config.yaml
```

**PRD** (Snowflake NSM):
```bash
cp .cursor/skills/prd/references/nsm-config.example.yaml \
   .cursor/skills/prd/references/nsm-config.yaml
```

## Updating

Edit files under `.cursor/skills/`, commit, and push. Teammates `git pull` to get updates.

## Notes

- **Personal MCP config** stays in `~/.cursor/mcp.json` — not in this repo.
- **Generated docs** go in `outputs/`.
- See `AI-INSTRUCTIONS.md` for methodology details.
