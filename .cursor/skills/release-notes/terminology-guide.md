# Terminology & Tone

## Tone Bar

- **Professional** — credible business comms, not a press release or sprint notes
- **Not childish** — no hype ("game-changer"), no baby talk ("we made things easier!")
- **Not engineering-heavy** — no arrow chains, canary steps, or unexplained phases
- **Voice test:** A new sales rep and finance analyst understand it; an engineer respects it as accurate

Max **one technical term per line**. Spell out acronyms on first use.

---

## Audience: Company-Wide (default)

- Internal audience slices OK ("100% of non-buyer-portal traffic") with brief context
- Jira ticket link optional on line 7: `[BXP-1155](url)`
- PRD link **required** on line 7: `– [PRD](url)`
- A/B test language OK; "statistically significant" only if user/data said so

---

## Audience: Customer-Facing

- No Jira or internal ticket links
- No internal codenames, phases, or team-only surfaces without plain explanation
- Rollout in customer language ("available on xometry.com") not internal traffic splits
- PRD link must be customer-safe (help doc, public release page) — ask if only internal PRD exists
- Line 7 format: `– [PRD](public-url)` or help doc link

---

## Term Handling

| Term type | Guidance | Example |
|-----------|----------|---------|
| Named product surfaces | Brief description | "Order History — where buyers view past orders" |
| Tech platform names | Explain role if used | "our previous website framework" not "Gatsby" alone |
| Internal project phases | Always explain | "Phase 2 of our website modernization" not "Phase 2" |
| Rollout mechanics | Summarize | "gradually rolled out" not "cookie override → 1% → 10% → 100%" |
| A/B test | OK (company-wide) | "an A/B test with buyer traffic" |
| Canary deploy | Simplify | "a staged rollout" |
| Acronyms | Spell out first use | "Search Results Page (SRP)" |
| Input arrows (→) | Never copy to output | Sanitize to plain prose |

**Rule:** If a term requires having attended a team meeting to understand it, add a short parenthetical.

---

## Link Format — Line 7

```
[TICKET-123](url) – [PRD](url)
```

| Link | Rule |
|------|------|
| PRD | **Required** |
| Ticket | Optional — omit entirely if not provided |
| Order | Ticket (if any), en-dash, PRD |

Customer-facing: PRD/customer doc only — no ticket.
