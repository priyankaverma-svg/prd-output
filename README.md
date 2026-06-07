# PRD Assistant

Cursor skill for product managers: structured 19-field PRD interview, critical review, 6-page docx export, and optional Jira handoff.

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

4. **Run the skill** in Agent chat:
   - Type `@prd`, or
   - Ask: *"Help me write a PRD"*

5. **Answer one question at a time** through the 19-field interview. The agent will review, export a 6-page docx, and optionally connect to Jira.

6. **Connect MCP tools** you need (optional Atlassian for Jira; Snowflake for impact baselines). Each person configures MCP in their own Cursor settings.

## What's in this repo

| Path | Purpose |
|------|---------|
| `.cursor/skills/prd/` | Main PRD assistant skill |
| `.cursor/skills/prd-codebase-scan/` | Codebase dependency scan (Field 13) |
| `AI-INSTRUCTIONS.md` | Human-readable workflow summary |
| `outputs/` | Generated PRD markdown and docx files |
| `requirements.txt` | Python deps for docx export |

## Skill files

```
.cursor/skills/prd/
├── SKILL.md                  # Main workflow — start here
├── interview-fields.md       # 19-field interview definitions
├── impact-analysis.md        # NSM / WBR / Snowflake / paste / manual
├── review-checklist.md       # Critical "check my work" audit
├── prd-output-template.md    # 6-page PRD structure
├── jira-handoff.md           # Epic + backlog / Confluence
├── references/
│   └── nsm-config.example.yaml
└── scripts/
    └── generate_prd_docx.py
```

## Team setup — NSM config

Copy and customize for your team's Snowflake views:

```bash
cp .cursor/skills/prd/references/nsm-config.example.yaml \
   .cursor/skills/prd/references/nsm-config.yaml
```

Edit `nsm-config.yaml` with approved query templates. The agent never invents SQL.

## Workflow

```
ENTRY → INTERVIEW (19 fields) → GENERATE → REVIEW → EXPORT → JIRA (optional)
```

- **REVIEW**: Agent critically audits the PRD, then asks apply all changes or show changes only
- **EXPORT**: 6-page `.docx` saved to `outputs/`
- **JIRA**: Optional Epic + backlog from functional requirements

## Maintainer — first-time push to GitHub

```bash
git init
git add .
git commit -m "Add PRD assistant skill for team"

# Create repo on GitHub → name: prd-output

git branch -M main
git remote add origin https://github.com/priyankaverma-svg/prd-output.git
git push -u origin main
```

## Updating the skill

Edit files under `.cursor/skills/`, commit, and push. Teammates `git pull` to get updates.

## Notes

- **Personal MCP config** stays in each user's `~/.cursor/mcp.json` — not in this repo.
- **Generated PRDs** go in `outputs/` — add your own project subfolders as needed.
- For methodology details, see `AI-INSTRUCTIONS.md` or ask in Agent with `@prd`.
