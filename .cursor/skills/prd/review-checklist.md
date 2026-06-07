# REVIEW — Critical PRD Audit

Run after GENERATE or when user pastes an existing PRD (ENTRY option 4).

## Audit Checklist

Score each item. Flag failures with severity.

### Completeness (19 fields)

| Check | 🔴 Must fix if |
|-------|----------------|
| Problem statement | Feature description instead of broken experience |
| Goals | Vague ("improve UX") with no outcomes |
| Persona | "Our users" with no role or pain point |
| Hypothesis | Missing If/Then/Because/Why Now |
| Primary metric | No named metric or no target |
| Secondary metrics | Fewer than 2 named |
| Guardrails | None defined |
| Happy path | No steps or only one step |
| Friction | Fewer than 2 friction + mitigation pairs |
| Edge cases | "Standard edge cases" or fewer than 2 categories |
| Functional reqs | Fewer than 3 P0 Given/When/Then |
| Non-functional | Missing performance, security, or accessibility |
| Dependencies | None listed when feature clearly touches systems |
| Assumptions | Missing business, functional, or technical |
| Risks | Fewer than 2 with mitigation |
| RACXI | All cells empty |
| Release strategy | "Just ship it" with no stages |
| FAQs | Fewer than 3 substantive Q&A pairs |

### Data Integrity

| Check | 🔴 Must fix if |
|-------|----------------|
| Metric provenance | Numbers present but no source labeled |
| Invented baselines | Agent or user claims numbers without source |
| Hypothesis ↔ metrics | Hypothesis names metric not in Section 3 |
| FR ↔ problem | P0 requirements don't address stated problem |

### Page Budget

| Check | 🟡 Should fix if |
|-------|------------------|
| Section 1–3 prose | More than 2 sentences per subsection |
| Happy path | More than 5 steps |
| Friction table | More than 3 rows |
| Edge cases | More than 3 bullets |
| Functional reqs | More than 6 FR items |
| FAQs | More than 3 or answers longer than 1 sentence |
| Total length | Likely exceeds 6 printed pages |

### Placeholders

| Check | Severity |
|-------|----------|
| `[Enter text]` without escalation note | 🔴 |
| `[Enter text]` with documented reason | 🟡 |
| Figma placeholder with no timeline | 🟡 |
| GTM "to be completed at launch" | 🟢 (expected) |

### Consistency

| Check | 🟡 Should fix if |
|-------|------------------|
| Checklist vs content | Checklist says Yes but section is Partial |
| P0 count vs launch scope | P0 items exceed realistic launch scope |
| Release strategy vs guardrails | No rollback trigger in release or guardrails |

---

## Review Output Format

```markdown
## PRD Review — [Project Name]

| # | Finding | Severity | Section | Recommendation |
|---|---------|----------|---------|----------------|
| 1 | [finding] | 🔴/🟡/🟢 | [section] | [specific fix] |

**Summary:** [N] must-fix, [N] should-fix, [N] optional
```

Then ask:

"I found [N] recommendations ([X] must-fix, [Y] should-fix, [Z] optional). Do you want me to **apply all changes**, or **show changes needed only**?"

### Apply All

Revise the full PRD markdown. Re-run page budget check. Proceed to EXPORT.

### Changes Only

List each recommendation with section reference. Wait for user to approve which to apply. Apply approved changes. Proceed to EXPORT.
