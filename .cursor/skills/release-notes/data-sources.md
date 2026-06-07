# Data Sources — Impact & Input

## Hard Rules

- Never invent SQL, baselines, or metric values
- Never assume Snowflake time window — ask if querying
- Never extrapolate dollar figures from percentages alone
- "Statistically significant" only if user or data source explicitly states it
- If Snowflake MCP errors → ask user to paste export or enter numbers manually

---

## Snowflake

**Use for:** Line 5 impact metrics only

**Requires:**
- User names metric or provides approved query/export
- Time window confirmed by user
- Approved mapping in `../brd/references/analytics-config.yaml` or `../prd/references/nsm-config.yaml`, OR user provides exact view/table

Use `run_snowflake_query` only with approved templates. No ad-hoc SQL.

**If unavailable:** "Snowflake isn't connected. Paste your dashboard/WBR export or share numbers directly?"

Record in line 5 only what was returned or pasted — label source mentally for user confirmation.

---

## Jira

**Use for:** Raw input via fix version or epic key

1. Ask project + fix version or epic key
2. Use Atlassian MCP to fetch shipped tickets
3. Synthesize into extract step — do not dump ticket list into 7 lines
4. Ticket link on line 7 is **optional**

---

## Paste or Upload

WBR CSV, experiment readout, dashboard screenshot, Statsig export.

Extract only what user provided. Ask user to confirm before writing.

---

## Manual

User states launch, rollout, and metrics verbatim.

---

## No Impact Metrics

User must reply **"No impact metrics"** explicitly.

- Skip line 5 impact content
- Do not use "improves performance", "reduces risk", or similar substitutes
- Early signal on line 6 only if user gave a specific number
