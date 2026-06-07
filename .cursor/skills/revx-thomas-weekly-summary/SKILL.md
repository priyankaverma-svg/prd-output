---
name: revx-thomas-weekly-summary
description: >-
  Reads #revx-thomas for a weekly date range, synthesizes a short Slack summary
  (not a transcript), adds a separate SOW compliance update against Phase 1/2
  baselines, and drafts to requester DM (test) or supplier channel (prod).
  Use for RevX Thomas weekly updates, SOW compliance, or scheduled Monday
  summaries.
---

# RevX Thomas Weekly Summary

Reads **#revx-thomas** for a Sun–Sat week, synthesizes leadership-ready Slack copy,
and adds a **separate SOW compliance** block. Default **test mode** = DM to requester.

**Config:** [references/config.md](references/config.md)
**Editorial:** [references/editorial-guardrails.md](references/editorial-guardrails.md)
**Output template:** [references/slack-output-template.md](references/slack-output-template.md)
**Automation:** [references/automation-prompt.md](references/automation-prompt.md)

## Non-Negotiable Rules

- **Synthesize themes — never transcribe** — see editorial guardrails
- **Two blocks** — channel summary + SOW compliance (separate, with `---`)
- **Never invent** status, completions, metrics, or SOW progress
- **Ignore Est. Hours** in all SOW references
- **Compact default** — ≤ 900 chars total; max 2 bullets/section, 15 words/bullet — see editorial guardrails
- **Omit empty sections** — no "None this week" padding
- **Test default** — DM to requester; prod channel only on explicit request
- **Week window** — Sunday 00:00 – Saturday 23:59 America/New_York unless user specifies dates

## Workflow

```
ENTRY → READ → SYNTHESIZE → SOW MAP → EDIT → CHECK → POST PROMPT
```

---

## ENTRY

Confirm if not provided:

1. **Week range** — e.g. `04/12/2026 – 04/18/2026` (Sun–Sat)
   - Scheduled runs: previous week ending yesterday (Saturday)
2. **Mode** — `test` (DM, default) or `prod` (`#supplier-new-leads-generation-internalonly`)

---

## READ

1. `slack_search_channels` → `#revx-thomas` (include private if needed)
2. `slack_read_channel` with `oldest` / `latest` Unix timestamps for the week
3. Paginate with `cursor` if more messages exist
4. `slack_read_thread` on high-activity parents
5. If Slack unavailable → ask user to paste channel export

---

## SYNTHESIZE

Fill channel sections per [slack-output-template.md](references/slack-output-template.md):

- Top discussion points
- Action items completed
- Upcoming action items
- Hotly debated
- Need focus / attention

Apply [editorial-guardrails.md](references/editorial-guardrails.md). No message-by-message lists.

---

## SOW MAP

Separate block using:

- [sow-phase1-baseline.md](references/sow-phase1-baseline.md) — open carryover items
- [sow-phase2-baseline.md](references/sow-phase2-baseline.md) — May 2026+ buckets
- [sow-dependencies.md](references/sow-dependencies.md) — blocked rules

Classify: On track · At risk · Blocked · No channel signal · Completed (with evidence)

Phase 2 is primary from May onward; SOW 1 in-progress items stay on radar.

---

## EDIT

1. Rewrite chat-log bullets → ≤ 15 words each
2. Merge duplicate themes across sections
3. **Count characters — must be ≤ 900**; cut per priority order in editorial guardrails

---

## CHECK

- [ ] **Total ≤ 900 characters**
- [ ] Not a transcript — synthesized themes only
- [ ] ≤2 bullets per section (≤1 for Done/Debate/Focus)
- [ ] Empty sections omitted
- [ ] SOW block ≤ 4 compact lines
- [ ] No invented SOW status or completions
- [ ] Test mode → DM only unless prod confirmed

**Example:** [examples.md](examples.md)

---

## POST PROMPT

**Test (default):**

> Ready to send this weekly summary to **your DM** for review?

- `slack_search_users` → Priyanka Verma (or requester name user gives)
- `slack_send_message_draft` to user `user_id` as `channel_id`
- Send directly only if user explicitly approves

**Prod:**

> Ready to post to **#supplier-new-leads-generation-internalonly**?

Only when mode = prod and user confirms.

Save optional: `outputs/revx-thomas-summary-{YYYY-MM-DD-week-end}.md`

---

## Scheduled automation

Every **Monday 7:00 AM America/New_York** — see [references/automation-prompt.md](references/automation-prompt.md) and repo `AUTOMATION.md`.
