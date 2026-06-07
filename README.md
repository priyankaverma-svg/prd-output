# BRD, PRD & Release Comms Assistant

Cursor skills for product and business teams: BRD/PRD interviews, 6-page docx export, release docs, newsletter launch slots, newsletter consolidation, and BRD → PRD handoff.

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
   - `@release-doc-writer` — long-form release one-pager (PM/Eng)
   - `@release-notes` — 7-line slot for `#pdt-releases` (PM/Eng)
   - `@release-newsletter-consolidator` — newsletter draft from `#pdt-releases` (Central Comms)

5. **BRD/PRD:** one question at a time → review → 6-page docx → optional handoff.

6. **Release comms (PM/Eng):** `@release-doc-writer` if needed → `@release-notes` → prompt to send to `#pdt-releases`.

7. **Newsletter (Central Comms):** `@release-newsletter-consolidator` → draft for executive leadership (human sends).

8. **Connect MCP tools** (optional): Slack (`#pdt-releases`), Snowflake, FullStory, Conviva, Atlassian.

## What's in this repo

| Path | Purpose |
|------|---------|
| `.cursor/skills/brd/` | BRD assistant — 17 fields + FAQ |
| `.cursor/skills/prd/` | PRD assistant — 19 fields |
| `.cursor/skills/prd-codebase-scan/` | Codebase dependency scan (PRD Field 13) |
| `.cursor/skills/release-doc-writer/` | Release one-pager (Calendar of Product Release Notes template) |
| `.cursor/skills/release-notes/` | 7-line slot for `#pdt-releases` |
| `.cursor/skills/release-newsletter-consolidator/` | Newsletter consolidation for Central Comms |
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

## Release comms workflow (PM/Eng)

```
@release-doc-writer (if no doc) → @release-notes → CHANNEL PROMPT → #pdt-releases
```

**Release doc** (`@release-doc-writer`):
```
ENTRY → GATHER → WRITE → REVIEW → EXPORT → HANDOFF
```
- Template: Calendar of Product Release Notes (see `release-doc-writer/references/`)
- PRD required; never invent metrics

**7-line slot** (`@release-notes`):
```
ENTRY → RELEASE DOC CHECK → EXTRACT → GATE → WRITE → CHECK → CHANNEL PROMPT
```
- Release doc required — hand off to `@release-doc-writer` if missing
- **7 lines** — professional, self-contained; PRD on line 7
- Routing tag for newsletter section (e.g. `[US · Buyer Experience]`)
- Prompts to send to `#pdt-releases` when ready (draft for review default)
- No mailto owner lead-in

## Newsletter consolidation (Central Comms)

```
@release-newsletter-consolidator: date range → read #pdt-releases → bucket → assemble → draft
```

- Reads slots PM/Eng posted in `#pdt-releases`
- Buckets by routing tag into fixed newsletter template
- Hands off draft — human sends to executive leadership
- Optional: reminder nudge to `#pdt-operations`

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

## Google Gemini (no Cursor required)

Use the same workflows in **Gemini Gems** — copy-paste instructions from the `gemini/` folder.

1. Open [gemini.google.com](https://gemini.google.com) → **Gem manager** → **New Gem**
2. Copy instructions from one of:
   - `gemini/release-doc-writer-gem-instructions.md` — release one-pager
   - `gemini/release-notes-gem-instructions.md` — 7-line slots
   - `gemini/release-newsletter-consolidator-gem-instructions.md` — newsletter consolidation
   - `gemini/brd-gem-instructions.md` — business case
   - `gemini/prd-gem-instructions.md` — product spec
   - `gemini/product-docs-suite-gem-instructions.md` — BRD + PRD in one Gem
3. Share the Gem with your team

See `gemini/README.md` for full setup. **Limitation:** Gemini has no Snowflake/Jira MCP — users paste data/exports manually. No automatic docx — copy markdown to Word.

## Updating

Edit files under `.cursor/skills/` or `gemini/`, commit, and push. Teammates `git pull` to get updates.

## Notes

- **Personal MCP config** stays in `~/.cursor/mcp.json` — not in this repo.
- **Generated docs** go in `outputs/`.
- See `AI-INSTRUCTIONS.md` for methodology details.
