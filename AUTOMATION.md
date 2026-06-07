# Cursor Automation — RevX Thomas Weekly Summary

## First report — scheduled in Slack

| Setting | Value |
|---------|--------|
| **Post at** | **Monday, June 8, 2026 · 7:00 AM ET** |
| **Channel** | `#supplier-new-leads-generation-internalonly` |
| **Window** | **Two weeks:** May 24 – June 6, 2026 |

First message is already scheduled in Slack. See `.cursor/skills/revx-thomas-weekly-summary/references/schedule.md`.

## Ongoing schedule (from June 15, 2026)

| Setting | Value |
|---------|--------|
| **Trigger** | Cron: `0 7 * * 1` (Monday 7:00 AM) |
| **Timezone** | America/New_York |
| **Week** | Previous Sunday – Saturday (one week) |

## Tools

- Read Slack
- Post to Slack
- Slack MCP (connected in Automations)

## Prompt

Copy from `.cursor/skills/revx-thomas-weekly-summary/references/automation-prompt.md`

## Test vs prod

| Mode | Destination |
|------|-------------|
| **test** (current) | DM to Priyanka Verma |
| **prod** | `#supplier-new-leads-generation-internalonly` |

Change `MODE: test` → `MODE: prod` in automation prompt when ready.

## Setup steps

1. Open Cursor → **Automations** → New automation
2. Name: `RevX Thomas Weekly Summary`
3. Trigger: Cron Monday 7 AM ET
4. Enable Read Slack + Post to Slack + Slack MCP
5. Paste prompt from `automation-prompt.md`
6. Point at `prd-output` repo (or wherever skill lives)
7. Save and enable

## Manual test

In Agent chat:

```
@revx-thomas-weekly-summary — week 04/12/2026–04/18/2026, test mode, DM to me
```
