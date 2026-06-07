# PRD Output Template

Hard limit: TOC page + 5 content pages = 6 pages when printed. Write tight. Compress ruthlessly.

## Page Budget

| Section | Max space |
|---|---|
| Title + TOC | Page 1 only |
| 1. Purpose & Objectives | 1/4 page |
| 2. Strategic Context | 1/4 page |
| 3. Impact & Metrics | 1/4 page |
| 4. UX Journey & Friction | 3/4 page |
| 5. Functional & Non-Functional Requirements | 1.25 pages |
| 6. Dependencies & Checklist | 1/4 page |
| 7. Assumptions, Risks & Constraints | 1/3 page |
| 8. Execution & Rollout | 1/3 page |
| 9. GTM Readiness | 2 lines |
| 10. FAQs | 1/4 page |

## Writing Rules

- Sections 1, 2, 3: max 2 sentences each
- Section 4: happy path max 5 numbered steps; friction as 2-col table max 3 rows; edge cases max 3 bullets
- Section 5: max 6 FR items total; non-functional max 3 bullets
- Section 7: max 2 bullets per category for assumptions, risks, constraints
- Section 8: RACXI table only — no explanatory prose; release strategy max 3 bullets
- Section 10: max 3 FAQs, 1 sentence answer each
- Bullets over prose in every section except Section 1

## PRD Structure

---

# [Project Name] — Product Requirements Document

| Project Name | [name] |
|---|---|
| Status | In Progress |
| Product Owner | [Field 17 accountable — or [Enter text]] |
| BRD Link | [include only if BRD was provided] |

## Table of Contents
| Section | Page |
|---|---|
| 1. Purpose & Objectives | 2 |
| 2. Strategic Context | 2 |
| 3. Impact & Metrics | 2 |
| 4. UX Journey & Friction Analysis | 3 |
| 5. Functional & Non-Functional Requirements | 3 |
| 6. PRD Checklist, Dependencies & Cross-Team Impact | 4 |
| 7. Assumptions, Risks & Constraints | 5 |
| 8. Execution & Rollout Plan | 5 |
| 9. GTM Readiness | 6 |
| 10. FAQs | 6 |

---

## 1. Purpose & Objectives
**1.1 Problem Statement** [Field 1]
Narrative paragraph: what is broken today, who experiences it, why it matters.

**1.2 Goals & Objectives** [Field 2]
- [Goal 1]
- [Goal 2]

---

## 2. Strategic Context
**2.1 User Persona(s)** [Field 3]
[Persona] needs [job to be done] but today [pain point].

**2.2 Hypothesis** [Field 4]
If we [change], then [outcome] because [reason], and now is the right time because [why now].

---

## 3. Impact & Metrics
**3.1 Business Metrics** [Fields 5, 6]
| Primary (North Star) | [metric]: [baseline] → target [target] ([window]) |
| Source | [WBR CSV / Snowflake / manual / user paste / NSM reference file — never omit] |
| Secondary | [2–3 supporting metrics] |

**3.2 Guardrail Metrics** [Field 7]
- [Metric]: must not [direction] by more than [threshold]

---

## 4. UX Journey & Friction Analysis
**4.1 Happy Path** [Field 8]
1. [Step 1]
2. [Step 2]
...
Figma: [link or placeholder]

**4.2 Friction Points & Mitigation** [Field 9]
| Friction | Mitigation |
|---|---|
| [Friction 1] | [Mitigation 1] |

**4.3 Edge Cases** [Field 10]
- User State: [handling]
- Regional: [handling]
- Data: [handling]

---

## 5. Functional & Non-Functional Requirements
**5.1 Functional Requirements** [Field 11]
[Functional Area]
- FR-001 (P0): Given [context] / When [action] / Then [outcome]
- FR-002 (P1): Given [context] / When [action] / Then [outcome]

**5.2 Non-Functional Requirements** [Field 12]
- Performance: [requirement]
- Security: [requirement]
- Accessibility: [requirement]

---

## 6. PRD Checklist, Dependencies & Cross-Team Impact
**6.1 Checklist**
| Item | Status |
|---|---|
| Problem statement defined | [Yes / Partial / No] |
| User persona validated | [Yes / Assumed / No] |
| Metrics and guardrails set | [Yes / Partial / No] |
| UX flows documented | [Yes / In progress / No] |
| Functional requirements complete | [Yes / Partial / No] |
| Non-functional requirements defined | [Yes / Partial / No] |
| Dependencies identified | [Yes / None / Pending] |
| RACXI complete | [Yes / Partial / No] |
| GTM plan initiated | No — to be completed at launch |

**6.2 Critical Dependencies** [Field 13]
- [Dependency]: owned by [team/system]

---

## 7. Assumptions, Risks & Constraints
**7.1 Assumptions** [Field 14]
- Business: [assumption]
- Functional: [assumption]
- Technical: [assumption]

**7.2 Risks** [Field 15]
- R1: [risk] → Mitigation: [approach]
- R2: [risk] → Mitigation: [approach]

**7.3 Constraints** [Field 16]
- C1: [constraint]

---

## 8. Execution & Rollout Plan
**8.1 RACXI** [Field 17]
Legend: R = Does the work | A = Final decision | C = Input needed | X = Approval gate | I = Kept in loop

| Phase | R | A | C | X | I |
|---|---|---|---|---|---|
| Discovery | | | | | |
| Design | | | | | |
| Development | | | | | |
| QA | | | | | |
| Launch | | | | | |

**8.2 Release Strategy** [Field 18]
- Internal/Alpha: [scope]
- Canary/Beta: [% traffic, duration]
- GA: [trigger condition]

---

## 9. GTM Readiness
[To be completed at launch — see GTM Checklist]

---

## 10. FAQs [Field 19]
**Q: [question]**
A: [answer]

**Q: [question]**
A: [answer]

**Q: [question]**
A: [answer]

*This is a living document. Update requirements, metrics, and checklist items as the feature evolves. Functional requirements are the source of truth for engineering until superseded by a technical spec.*
