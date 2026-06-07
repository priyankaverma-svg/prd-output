# Cursor Automation — RevX Thomas Weekly Summary

## Schedule

| Setting | Value |
|---------|--------|
| **Trigger** | Cron: `0 7 * * 1` (Monday 7:00 AM) |
| **Timezone** | America/New_York |
| **Week** | Previous Sunday – Saturday (week ending yesterday) |

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
