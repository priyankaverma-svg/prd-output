# SOW dates — required in compliance output

Every SOW compliance bullet must include a **date or timeline** for the deliverable mentioned.

## Date sources (priority order)

1. **SOW baseline** — `Timeline` column in phase1/phase2 baselines
2. **Channel evidence** — explicit date in `#revx-thomas` this week (e.g. "follow-up early next week")
3. **User confirmation** — user provides when asked in SOW DATE GATE

Never invent dates. Never write "TBD" in final output without asking user first.

## Missing date = GATE before finalize

If a deliverable appears in the SOW compliance draft and baseline shows `—`, `TBD`, empty, or `Week X–Y` without calendar dates, **stop and ask**:

> For *[deliverable name]*, the SOW has no firm date yet. What target date or week should I use in this summary? (Or reply "skip" to omit from this week.)

Ask **once per missing item**, batched in one message. Do not post until user responds or says skip.

After user provides dates, offer:

> Should I update `sow-phase1-baseline.md` or `sow-phase2-baseline.md` with these dates for future weeks?

## Output format

Each SOW bullet = **deliverable + date context + status**:

```
• Lead assignment in Salesforce (target: Week 7–8, date pending update) is at risk because routing for incomplete records is still unsettled.
• First-touch attribution (completed) direction is set and matches leadership’s two-field approach.
• Company ID alignment (Week 4–5, not yet started) had no channel update this week.
```

## Completed items

Include completion context if known: `(completed)` or `(completed, Week 2–3)`.

## Phase 2 (May onwards)

Use baseline timeline when present. If bucket has no calendar date, ask before including in compliance block.
