# Cursor Automation — prompt body

Use when creating scheduled automation: **Every Monday 7:00 AM America/New_York**.

```
Run @revx-thomas-weekly-summary for the completed week ending yesterday (Saturday).

Week window: previous Sunday 00:00 – Saturday 23:59 America/New_York.

MODE: test — DM summary to Priyanka Verma only. Do NOT post to #supplier-new-leads-generation-internalonly unless this prompt says MODE: prod.

Steps:
1. Read #revx-thomas including threads (Slack MCP).
2. Synthesize COMPACT per editorial-guardrails.md — ≤900 chars total, themes only, never transcript.
3. Build separate SOW compliance block using sow-phase1-baseline, sow-phase2-baseline, sow-dependencies.
4. Ignore Est. Hours. Never invent status or metrics.
5. Run CHECK from SKILL.md.
6. slack_send_message_draft to Priyanka Verma DM (test) or send on explicit approval.

Repo skill: .cursor/skills/revx-thomas-weekly-summary/SKILL.md
```

## Cron (if timezone set to America/New_York in editor)

`0 7 * * 1` — every Monday 7:00 AM

## Tools

- Read Slack
- Post to Slack
- Slack MCP (dashboard-connected)

## Switch to production

Change prompt: `MODE: prod` and destination `#supplier-new-leads-generation-internalonly`.
