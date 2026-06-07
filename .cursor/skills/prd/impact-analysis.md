# Impact Analysis — Fields 5–7

Run this fork **before Field 5**. Fields 6–7 inherit the same source unless the user changes it.

## Hard Rules

- Never invent SQL, baselines, or metric values
- Never assume Snowflake 90d — ask window every time
- Label every metric with its data source
- If Snowflake MCP errors → offer WBR paste, file upload, or manual

---

## Step 5a — Data Source (ask first)

[Impact & Metrics · Field 5a]
Context: Impact metrics need a trusted baseline — we establish how before asking for numbers.

Ask:

"How should we establish impact baselines for this feature?
1. I'll provide metrics manually
2. Use a team NSM reference file (I'll point you to it)
3. Paste or upload data (WBR export, dashboard CSV, Snowflake result, screenshot table)
4. Pull from Snowflake (I have known tables/views)
5. Skip quant — qualitative impact only for now"

---

## Option 1 — Manual

Proceed to Field 5b. User states metric, baseline, target verbatim.

---

## Option 2 — Team NSM Reference File

Ask: "What's the path to your NSM config? (Default: `references/nsm-config.yaml` in this skill folder, or your team copy.)"

Load the file. Ask which NSM applies to this feature. Ask which segment (checkout path, upload path, teamspace, other).

Only run query templates defined in the config — no ad-hoc SQL.

Pre-fill baseline from config query results. Ask user to confirm target.

Record source as: `NSM reference file — [filename]`

---

## Option 3 — Paste or Upload

Ask: "Paste a table, upload a CSV, or share a WBR/dashboard export. What NSM does this map to, and what time window does it cover?"

Extract only what the user provided. If ambiguous, escalate before filling Fields 5–7.

Record source as: `WBR CSV` / `user paste` / `dashboard export` / `uploaded file — [name]`

---

## Option 4 — Snowflake (controlled)

Requires ALL of:
- NSM name confirmed by user
- Segment/funnel step confirmed
- Time window confirmed (30d / 90d / other — ask, don't assume)
- Approved mapping in `references/nsm-config.yaml` OR user provides exact view/table + column names

If no mapping exists → fall back to Option 3 (paste export) or Option 1 (manual).

Use Snowflake MCP (`run_snowflake_query`) only with templates from the reference file. Substitute parameters: `{{nsm}}`, `{{segment}}`, `{{window_days}}`.

If MCP unavailable or errors:

"Snowflake isn't available. Would you like to paste your WBR/export, upload a file, or enter metrics manually?"

Record source as: `Snowflake — [view/table], [window]`

---

## Option 5 — Skip Quant

Fields 5–7 get qualitative placeholders:
- Primary: `[Baseline TBD — no quant source provided]`
- Secondary: `[TBD]`
- Guardrail: `[TBD — define before launch]`

Checklist: `Metrics and guardrails set | Partial`

---

## Field 5b — Primary Metric

After data source is resolved, ask (or confirm pre-filled):

"What is the single most important metric that will tell you this feature was a success?"

If baseline was pre-filled: "Here's what I extracted: [baseline, source, window]. What's your target?"

FILLED: named metric with direction and target
EMPTY: "improve engagement", metric with no target
Escalation: "What specific number moves if this works — and what does it need to move from and to?"

---

## Field 6 — Secondary Metrics

Ask: "What secondary metrics will you track alongside the primary one?"

If data was pasted/uploaded, suggest metrics visible in the source. User confirms.

FILLED: 2–3 named secondary metrics
EMPTY: "other metrics", "various KPIs"
Escalation: "Name 2–3 specific metrics you'd check in your dashboard a month after launch."

---

## Field 7 — Guardrail Metrics

Ask: "What metrics must not get worse when this ships — what would tell you the feature caused harm even if the primary metric improved?"

FILLED: 1–3 named guardrail metrics with thresholds if available
EMPTY: "nothing", "everything should be fine"
Escalation: "What would you check to make sure you haven't broken something else? What's your rollback trigger?"

---

## PRD Section 3 Output Format

Every metric block must include provenance:

```markdown
**3.1 Business Metrics**
| Primary (North Star) | [metric]: [baseline] → target [target] ([window]) |
| Source | [WBR CSV / Snowflake / manual / user paste / NSM reference file] |
| Secondary | [2–3 metrics] |

**3.2 Guardrail Metrics**
- [Metric]: must not [direction] by more than [threshold]
```
