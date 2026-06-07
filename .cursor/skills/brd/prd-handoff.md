# PRD Handoff — Post-BRD Export

Run after BRD docx is generated and user confirms BRD is ready for solution design.

## Ask

"BRD complete. Do you want to start the PRD now?
1. Yes — begin PRD interview using this BRD as input
2. No — done for now"

---

## Option 1 — Start PRD

1. Load the [prd](../prd/SKILL.md) skill (`@prd`)
2. Use PRD ENTRY option 2: "I have a BRD — I want to build the PRD now"
3. Pass the finalized BRD markdown or docx content as context
4. PRD still asks all 19 fields — use BRD to pre-fill and sharpen questions
5. Mark BRD fields already covered; start at first PRD field needing new detail

**Pre-fill mapping:**

| BRD field | PRD field |
|-----------|-----------|
| Fields 1–2 (WHO, WHAT) | Field 1 Problem Statement |
| Field 9 Desired outcome | Field 2 Goals |
| Field 1 WHO | Field 3 Persona |
| Fields 3, 5, 9 | Fields 5–7 Metrics |
| Field 8 Current state | Field 8 Happy path (inverse — what breaks) |
| Field 11 Financial | Informs Field 5 primary metric target |

6. Update Appendix A checklist row: `PRD Initiated | Yes — [date]`

---

## Option 2 — Done

Provide deliverables:
- `outputs/[project-name]-brd.md`
- `outputs/[project-name]-brd.docx`
- Reminder: run `@prd` when ready for solution design
