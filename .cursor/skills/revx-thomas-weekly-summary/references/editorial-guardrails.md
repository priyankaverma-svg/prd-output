# Editorial Guardrails

## Core rule

**Synthesize themes — never transcribe the channel.**

The reader gets what mattered and what to do, not a play-by-play of who said what when.

## Abstraction

| Do | Don't |
|----|--------|
| Roll related messages into one bullet | One bullet per Slack message |
| Name decisions and outcomes | List every participant |
| Max 2–4 bullets per section | Exhaustive thread replay |
| Merge duplicate threads | Repeat same topic across sections |

## Voice (Slack-optimized)

- Each bullet ≤ 1–2 lines
- Active voice: "Campaign_Name_v2 UAT started" not "There was discussion about…"
- Spell out acronyms once: HubSpot (HS), Salesforce (SF), Marketing Qualified Lead (MQL)
- No filler: cut "FYI", "quick update", "as discussed", emoji noise
- No timestamps unless deadline is the point

## Exclude

- Updates with no decision ("working on X") unless SOW status changes
- Social / off-topic / reactions-only
- Long technical dumps — compress to outcome
- Verbatim quotes unless exact wording is a decision record

## Section bars

| Section | Bar |
|---------|-----|
| Top discussion points | 3–5 **themes**, not people posting |
| Action items completed | Clear done signal only: shipped, merged, signed off, closed ticket |
| Upcoming action items | Forward-looking + @owner when known |
| Hotly debated | Real disagreement or open fork — not "long thread" alone |
| Need focus / attention | Blockers, missed deadlines, escalations, silent P0 SOW items |

## SOW compliance block

- Map signal → **SOW ID + status delta** — not message recap
- Baseline status + weekly evidence only
- **"No channel signal"** is valid — do not invent progress
- Never mark on track because topic was merely mentioned

## EDIT step

Before CHECK, rewrite any bullet that reads like a chat log. Combine related points. Cut noise.

## Anti-pattern

**Bad:** Priyanka said X. Max replied Y. Uwa asked Z.

**Good:** *Attribution:* MarOps alignment open on Create Date — blocks Bucket 4.1.
