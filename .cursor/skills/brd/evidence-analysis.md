# Evidence & Impact Analysis — Data Sources

Run **once after ENTRY**, before Fields 3–5. Reuse the same sources for Fields 8 and 11 unless the user changes them.

## Hard Rules

- Never invent SQL, baselines, session data, or Conviva metrics
- Never assume Snowflake 90d — ask window every time
- Label every number with its data source in the BRD
- If any MCP errors → offer paste/upload or manual

---

## Step 0 — Connected Tools Check

[Data Sources · Pre-Field 3]
Context: Evidence and impact need trusted data — we establish what's available before asking for numbers.

Ask:

"For evidence and impact, which data sources do you have connected in Cursor — and should we use them for this BRD?

1. **Snowflake** — warehouse metrics (volume, conversion, revenue exposure)
2. **FullStory** — session replay / behavioral evidence (friction, drop-off examples)
3. **Conviva** — experience/video analytics (QoE, engagement)
4. **Paste or upload** — WBR, dashboards, tickets, exports
5. **Manual only** — I'll provide numbers
6. **Skip quant** — qualitative BRD for now

You can pick multiple. Which apply?"

For each selected tool, confirm it is actually connected. If not connected, offer paste/manual for that tool.

---

## Snowflake

**Use for:** Fields 3, 5, 11 — measurable outcome, business impact, financial impact

**Requires:**
- NSM or metric name confirmed by user
- Segment/funnel step confirmed
- Time window confirmed (ask — don't assume 90d)
- Approved mapping in `references/analytics-config.yaml` OR user provides exact view/table + columns

**MCP:** `run_snowflake_query` — only with templates from reference file. No ad-hoc SQL.

**If unavailable:** "Snowflake isn't connected. Paste a WBR/export, upload a file, or enter numbers manually?"

**Record source as:** `Snowflake — [view/table], [window]`

---

## FullStory

**Use for:** Fields 4, 8 — evidence (Tier 2), current state examples

**Requires user to provide one of:**
- Session ID
- User email or identifier (for `fullstory_sessions_for_user`)
- Specific page/feature + time range to investigate

**MCP tools:**
- `fullstory_sessions_for_user` — find sessions
- `fullstory_session_events` — event timeline for a session

**Classify as:** Tier 2 evidence (behavioral research) unless user provides statistical export

**Limitation:** Session-level data — not aggregate funnel metrics without user export

**If unavailable:** Paste FullStory export, screenshot, or describe sessions manually

**Record source as:** `FullStory — session [id] / user [identifier]`

---

## Conviva

**Use for:** Fields 4, 5 — experience evidence, impact on engagement/QoE

**Requires:**
- Call `mcp_auth` for server `user-conviva` if not authenticated
- User names which Conviva metric/dashboard maps to this problem
- User confirms what to query — do not invent Conviva API calls

**If unavailable or unauthenticated:** "Conviva isn't connected. Paste a dashboard export or enter metrics manually?"

**Record source as:** `Conviva — [metric/dashboard name]`

---

## Paste or Upload

Ask: "Paste a table, upload a CSV, or share a WBR/dashboard/ticket export. What does it map to, and what time window?"

Extract only what the user provided.

**Record source as:** `WBR CSV` / `user paste` / `dashboard export` / `uploaded file — [name]`

---

## Manual

User states numbers verbatim for Fields 3, 5, 11. No fabrication.

---

## Skip Quant

Fields 3, 5, 11 get placeholders with help tips. Evidence Field 4 may still be Tier 3–4.

---

## Evidence Tiers (Field 4)

Classify internally — do not show tier menu to user:

| Tier | Source examples |
|------|-----------------|
| 1 | Snowflake query, analytics export, A/B results |
| 2 | FullStory sessions, user interviews, surveys |
| 3 | Support tickets, sales escalations, NPS |
| 4 | Hypothesis — not validated |

Tell user: "Based on what you've shared, this is Tier [X] evidence — [one line on what would strengthen it]."

**Tier 4 mandatory 3-step sequence** (from interview-fields.md) before Field 4 is FILLED.

---

## BRD Output — Source Labels

Every quantified field in Section 1 and 4 must show provenance:

```markdown
| Source | [Snowflake / FullStory / Conviva / WBR CSV / manual / user paste] |
```
