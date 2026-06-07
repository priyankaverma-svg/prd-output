# Editorial Guardrails

## Core rule

**Short executive brief in plain English** — coherent sentences a non-technical leader can read aloud without decoding.

## Voice test

Read each bullet aloud. If it sounds like a Slack tag line, a ticket ID, or a fragment — rewrite as a full sentence.

## Hard limits

| Limit | Value |
|-------|-------|
| **Total message** | ≤ 1,100 characters (both blocks) |
| **Bullets per section** | Max **2**; prefer **1** |
| **Each bullet** | One **complete sentence** — subject, verb, outcome |
| **Empty sections** | Omit entirely |

If over 1,100 chars, drop lowest-priority section (Debate → Done detail → second Top bullet).

## Acronyms and jargon — avoid

| Don't use | Use instead |
|-----------|-------------|
| SF, HS | Salesforce, HubSpot |
| SDR | sales rep (or spell out once) |
| MQL, SQL | marketing qualified lead, sales qualified lead |
| 1.7, 1.6, MOP-3602 in summary | Plain deliverable name: "first-touch attribution", "lead assignment" |
| interim, quiet, delta, TBD | plain status: "still open", "no update this week" |
| first+last, URL/phone | "first touch and last touch", "website or phone number" |
| z-archive | "archived forms" |

**Allowed without spelling out:** RevX, Thomas, names of people.

## Sentence style

| Do | Don't |
|----|--------|
| Full sentences with context | Semicolon chains (`A; B; C`) |
| One idea per bullet | Telegram tags (`Attribution: first+last agreed`) |
| Plain words over internal shorthand | `disqualify logic`, `property mapping`, `routing not HS delay` |
| Say who does what when owner matters | `Jatinder:` colon-only fragments |

**Good:** Leadership agreed to show first-touch and last-touch campaign credit in two fields while campaign-level reporting is still being defined.

**Bad:** First+last touch agreed interim; campaign property mapping still open.

## Sections

| Section | Label | Content |
|---------|-------|---------|
| Top | `*Top discussion*` | 1–2 decisions or themes in full sentences |
| Done | `*Completed*` | What actually finished — skip routine MoM posts |
| Next | `*Next steps*` | 1–2 forward actions with owner name in prose |
| Debate | `*Open debate*` | One unresolved disagreement in plain language |
| Focus | `*Needs attention*` | Top blocker or decision still open |
| SOW | `*SOW compliance*` | 2–3 sentences — no item numbers |

## SOW block

Every bullet must include **deliverable name + date/timeline + status** in one sentence.

Date from baseline, channel, or user (after SOW DATE GATE). See [sow-date-rules.md](sow-date-rules.md).

```
*SOW compliance*
• First-touch attribution (completed) direction is set and matches leadership’s two-field approach.
• Lead assignment in Salesforce (target: Week 7–8, date pending update) is at risk because routing for incomplete records is still unsettled.
• Company ID alignment (Week 4–5, not yet started) and campaign name fix (Week 6–7) had no channel update this week.
```

No `On track:` / `At risk:` / `Quiet:` prefixes. No numbered line items unless user asks.
If baseline date is missing, **ask user before final output** — do not publish dateless SOW bullets.

## EDIT step

1. Replace every acronym and SOW ID with plain English
2. Split semicolon chains into separate bullets or one full sentence
3. Read-aloud test each bullet
4. Count characters — trim to ≤ 1,100 without sacrificing coherence

## Anti-patterns

**Fragment:** `Quiet: 1.4, 1.5, Phase 2 — no April signal`

**Coherent:** No channel update this week on company matching, campaign name fix, or May scope.
