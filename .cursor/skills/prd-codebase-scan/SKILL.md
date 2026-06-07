---
name: prd-codebase-scan
description: >-
  Analyzes an open codebase to extract PRD dependencies, data model impacts,
  third-party integrations, and technical risks. Use during PRD Field 13 when the
  user chooses Cursor scan, or when mapping feature scope to existing services
  and APIs.
---

# PRD Codebase Scan

Analyzes the open codebase to pre-fill PRD Field 13 (Critical Dependencies) and Field 15 (Risks).

## When to Use

- User is on PRD Field 13 and chooses **Cursor scan**
- User asks to identify dependencies or technical risks for a feature against the current repo

## Inputs Required

Before scanning, collect from the PRD interview (or ask if missing):

- **Feature context**: problem statement (Field 1)
- **Feature scope**: goals and objectives (Field 2)

## Analysis Workflow

With the relevant repo open, analyze and return:

1. All services and APIs this feature would touch
2. Data models that would need to change
3. Third-party dependencies introduced or affected
4. Technical risks based on current code structure and patterns
5. Any existing code that conflicts with or needs modification for this feature

## Output Format

Return structured findings:

```markdown
## Dependencies (Field 13)
- [Dependency]: owned by [team/system] — [brief rationale]

## Technical Risks (Field 15)
- R1: [risk] → Mitigation: [approach]
- R2: [risk] → Mitigation: [approach]

## Data Model Changes
- [model/table]: [change needed]

## Code Conflicts / Modifications
- [file/module]: [what needs to change]
```

## Handoff Back to PRD Interview

After presenting findings:

1. Ask user to confirm or correct each dependency and risk
2. Pre-fill Field 13 and Field 15 with confirmed items
3. Skip Field 15 interview question — move directly to Field 16
4. Note in the final PRD: "Dependencies and risks extracted via Cursor codebase analysis"

## Standalone Prompt (copy-paste)

If the user needs a prompt to run in a separate session:

```
Feature context: [problem statement from Field 1]
Feature scope: [goals from Field 2]

With this codebase open, please analyze and return:
1. All services and APIs this feature would touch
2. Data models that would need to change
3. Third-party dependencies introduced or affected
4. Technical risks based on current code structure and patterns
5. Any existing code that conflicts with or needs modification for this feature
```
