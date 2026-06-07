# Cursor Automation — prompt body

Use when creating scheduled automation: **Every Monday 7:00 AM America/New_York**.

```
Run @revx-thomas-weekly-summary for the completed week ending yesterday (Saturday).

Week window: previous Sunday 00:00 – Saturday 23:59 America/New_York.

MODE: test — DM summary to Priyanka Verma only. Do NOT post to #supplier-new-leads-generation-internalonly unless this prompt says MODE: prod.

Steps:
1. Read #revx-thomas including threads (Slack MCP).
2. Synthesize per editorial-guardrails.md — plain English full sentences, ≤1100 chars, no acronyms, never transcript.
3. Build SOW compliance block — deliverable + date (when in baseline) + status. Missing SOW dates → add needs-attention bullets; never invent dates or block the post.
4. Ignore Est. Hours. Never invent status, metrics, or dates.
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
