# JIRA Handoff — Post-Export

Run after the 6-page docx is generated. Requires Atlassian MCP.

## Ask

"Do you want to connect this PRD to Jira?
1. Link only — attach PRD to an existing Epic
2. Epic + backlog — create Epic and tickets from functional requirements
3. Confluence + Jira — publish PRD page and link to Epic
4. No — done"

---

## Option 1 — Link Only

Ask: "What's the Jira Epic or issue key to link? (e.g., BXPR-1234)"

Use `getJiraIssue` to fetch the issue. Use `addCommentToJiraIssue` or `editJiraIssue` to add:
- PRD docx path
- PRD markdown summary (problem + primary metric + P0 count)
- Link to Confluence page if one exists

---

## Option 2 — Epic + Backlog

**CRITICAL: Create Epic FIRST, then child tickets.**

### Step 1 — Project key

Ask: "Which Jira project? (e.g., BXPR, BXNE, PRODUCT)"

If unsure, call `getVisibleJiraProjects`.

### Step 2 — Present breakdown

From PRD Field 11, show planned Epic + tickets:

```
Epic: [Feature name from Field 1]
├── Story: FR-001 (P0) — [summary]
├── Story: FR-002 (P0) — [summary]
├── Story: FR-003 (P1) — [summary]
```

Ask user to confirm or adjust before creating.

### Step 3 — Create Epic

```
createJiraIssue(
  cloudId="...",
  projectKey="...",
  issueTypeName="Epic",
  summary="[Feature name]",
  description="[Problem statement + hypothesis + primary metric + docx path]"
)
```

Capture Epic key (e.g., `BXPR-1500`).

### Step 4 — Create child tickets

For each P0 and P1 FR:

```
createJiraIssue(
  cloudId="...",
  projectKey="...",
  issueTypeName="Story",
  summary="FR-001: [short title]",
  description="Given [context] / When [action] / Then [outcome]",
  parent="[Epic key]",
  additional_fields={"priority": {"name": "High"}}
)
```

### Step 5 — Summary

Present all created items with Jira links. Add Epic key to PRD metadata table.

---

## Option 3 — Confluence + Jira

### Step 1 — Space

Ask: "Which Confluence space should I publish the PRD to?"

Use `getConfluenceSpaces` if unsure.

### Step 2 — Create page

```
createConfluencePage(
  cloudId="...",
  spaceId="...",
  title="[Project Name] — PRD",
  body="[PRD markdown content]"
)
```

### Step 3 — Link to Jira

Create or update Epic (Option 2 Steps 3–4) with Confluence page URL in description.

---

## Option 4 — Done

Provide final deliverables:
- `[project-name]-prd.md`
- `[project-name]-prd.docx`
- Jira Epic key (if created)
- Confluence URL (if published)
