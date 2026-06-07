# Editorial Guardrails

## Core rule

**Synthesize themes — never transcribe.** Leadership skim-reads in under 60 seconds.

## Hard length limits (non-negotiable)

| Limit | Value |
|-------|-------|
| **Total message** | ≤ 900 characters (both blocks combined) |
| **Bullets per section** | Max **2**; use **1** when possible |
| **Words per bullet** | Max **15** |
| **SOW block total bullets** | Max **4** (combine statuses) |
| **Empty sections** | **Omit** the section header entirely |
| **Footer** | One line: `_#revx-thomas · {week}_` — no message counts, no amendment essay |

If over limit after EDIT, cut lowest-priority bullets until under 900 chars.

## Abstraction

| Do | Don't |
|----|--------|
| One theme = one short bullet | Multi-clause bullets with semicolons |
| Merge related topics | Separate bullets for same theme |
| Drop "completed" admin noise | List every doc share and MoM |
| Combine SOW items: `1.5–1.6 in progress` | One bullet per SOW line when status unchanged |

## Voice

- Telegram-style: noun + outcome (`Attribution: first+last touch agreed`)
- No sub-bullets, no parentheticals, no "team discussed"
- Acronyms OK if widely known (HS, SF); spell out once only if needed
- Active voice only

## Section priority (cut in this order if too long)

1. Drop *Hotly debated* if same theme already in *Top*
2. Merge *Done* into *Top* as past-tense clause
3. Trim *Next* to owner + action only (no meeting names)
4. SOW: one line for on-track, one for at-risk, one for quiet items combined

## Section bars

| Section | Max bullets | Content |
|---------|-------------|---------|
| Top | 2 | Decisions + themes only |
| Done | 1 | Biggest completions; omit if none material |
| Next | 2 | Owner + verb; highest priority only |
| Debate | 1 | Single open fork |
| Focus | 1 | Top blocker or decision |
| SOW | 4 | Status deltas only — not a registry |

## SOW block (compact)

Format as tight status lines, not subsections:

```
*SOW*
• On track: {ids} — {3-5 word delta}
• At risk: {ids} — {why}
• Quiet: {ids combined} — no signal
```

Skip "In progress (no weekly delta)" — fold into Quiet or omit.
Skip "Amendments in effect" unless user asks.
Skip Phase 2 mention when week is pre-May unless relevant.

## EDIT step

1. Count characters — must be ≤ 900
2. Shorten every bullet to ≤ 15 words
3. Delete duplicate themes across sections
4. Remove any bullet that restates another

## Anti-pattern

**Bad (too long):** Inclusion/exclusion: Team reviewed Tigran's comments on criteria doc; RevX will publish updated inclusion list. Z-archive forms stay for history only.

**Good:** Inclusion list update in flight; z-archive = history only.
