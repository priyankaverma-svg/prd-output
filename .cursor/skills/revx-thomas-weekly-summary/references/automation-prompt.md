# Cursor Automation — prompt body

Use when creating scheduled automation: **Every Monday 7:00 AM America/New_York**.

```
Run @revx-thomas-weekly-summary for the completed reporting window.

Week window: previous Sunday 00:00 – Saturday 23:59 America/New_York (one week).
Exception: first production run already scheduled for 6/8/2026 covering two weeks (5/24–6/6).

MODE: prod — post to #supplier-new-leads-generation-internalonly (C0AR8GURAMT).
Test DM only when user explicitly says MODE: test.

Steps:
1. Read #revx-thomas including threads (Slack MCP).
2. Synthesize per editorial-guardrails.md — plain English full sentences, ≤1100 chars, no acronyms, never transcript.
3. Build SOW compliance block — deliverable + date (when in baseline) + status. Missing SOW dates → add needs-attention bullets; never invent dates or block the post.
4. Ignore Est. Hours. Never invent status, metrics, or dates.
5. Run CHECK from SKILL.md.
6. PROD: slack_schedule_message (Monday 7 AM ET) or slack_send_message — auto-send, no draft, no review wait. TEST only: optional DM draft.

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
