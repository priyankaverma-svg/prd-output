# Google Gemini Gems — Setup Guide

Use these instruction files to recreate the Cursor skills in **Google Gemini** (Gemini Advanced → **Gem manager** → **New Gem**).

**Repo:** https://github.com/priyankaverma-svg/prd-output

---

## Quick setup (per Gem)

1. Open [gemini.google.com](https://gemini.google.com) → **Gem manager** (or Settings → Gems)
2. Click **New Gem**
3. **Name** and **Description** — see table below
4. **Instructions** — copy the full contents of the matching file in this folder
5. *(Optional)* **Knowledge** — upload `examples.md` from `.cursor/skills/release-notes/` for the Release Notes Gem
6. Save and share the Gem with your team (Google Workspace sharing if available)

---

## Which Gem to create

| Gem name | Instructions file | When to use |
|----------|-------------------|-------------|
| **Release Doc Writer** | `release-doc-writer-gem-instructions.md` | Long-form release one-pager (PM/Eng) |
| **Release Notes Writer** | `release-notes-gem-instructions.md` | 7-line slot for #pdt-releases (PM/Eng) |
| **Newsletter Consolidator** | `release-newsletter-consolidator-gem-instructions.md` | Newsletter draft (Central Comms) |
| **BRD Assistant** | `brd-gem-instructions.md` | Business case — WHAT & WHY |
| **PRD Assistant** | `prd-gem-instructions.md` | Product spec — HOW |
| **Product Docs Suite** *(optional)* | `product-docs-suite-gem-instructions.md` | BRD + PRD in one Gem |

---

## Gemini vs Cursor differences

| Feature | Cursor (`@skill`) | Gemini Gem |
|---------|-------------------|------------|
| Skills auto-load | Yes, from repo or `~/.cursor/skills/` | Paste instructions once per Gem |
| Snowflake / Jira MCP | Yes, if connected | **No** — user must paste data/exports |
| docx export script | `python generate_*_docx.py` | Copy markdown output; paste into Word |
| One question at a time | Enforced in BRD/PRD skills | Tell Gem in instructions (included) |
| Updates | `git pull` | Re-copy instructions when repo updates |

---

## Team sharing

- **Google Workspace:** Share Gems from Gem manager with your org
- **Without Gem sharing:** Share this repo link; teammates create their own Gems from these files
- **Pin the repo:** `git clone https://github.com/priyankaverma-svg/prd-output.git`

---

## Suggested Gem descriptions (for Gemini UI)

**Release Doc Writer:**
> Fills the Calendar of Product Release Notes template. What it Is, Why it Matters, Key Benefits, NSMs, Kudos, Visuals. PRD required.

**Release Notes Writer:**
> 7-line newsletter slot for #pdt-releases. Checks for release doc first. Routing tag + channel prompt. PRD required.

**Newsletter Consolidator:**
> Reads #pdt-releases for a date range, buckets by section, assembles newsletter draft for executive leadership.

**BRD Assistant:**
> Guides a 17-field business requirements interview. WHAT and WHY only. 6-page doc with appendix checklist.

**PRD Assistant:**
> Guides a 19-field product requirements interview. HOW to build. 6-page doc. Accepts approved BRD as input.
