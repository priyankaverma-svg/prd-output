# Interview Fields — 19 Fields in Order

### Field 1 — Problem Statement
[Purpose & Objectives · Field 1 of 19]
Context: Grounds the PRD in the problem being solved — engineers need to understand WHY before they build HOW.
Ask: "In your own words, what is the problem or gap this feature is solving? What is broken, missing, or painful today for the user?"
FILLED: clear description of the broken experience with enough context for an engineer to understand the motivation
EMPTY: a feature description ("we want to build X") or one-liner with no context
Escalation: "What does a user experience today that this feature fixes? Walk me through what's broken right now."

---

### Field 2 — Goals & Objectives
[Purpose & Objectives · Field 2 of 19]
Context: Defines what success looks like — the outcomes engineering and design are building toward.
Ask: "What are you trying to achieve? List the specific goals — what does success look like when this ships?"
FILLED: 2–4 specific, outcome-oriented goals
EMPTY: "improve the experience", vague improvement language
Escalation: "Name 2–3 specific things that will be true after this ships that aren't true today."

---

### Field 3 — User Persona(s)
[Strategic Context · Field 3 of 19]
Context: Identifies who is using this feature and what drives their behavior.
Ask: "Describe the primary user — their role, what they're trying to accomplish, and what frustrates them today."
FILLED: named/described persona with job-to-be-done and a pain point
EMPTY: "our users", "customers" with no detail
Escalation: "Who specifically is doing this task — what's their role, and what does their day look like when this problem hits them?"

---

### Field 4 — Hypothesis
[Strategic Context · Field 4 of 19]
Context: The testable bet at the center of this feature — connects the change to the expected outcome.
Draft the hypothesis from Fields 1–3 using this format:
"If we [change/feature], then [metric/outcome] because [reason], and now is the right time because [why now]."
Present it: "Based on what you've shared, here's a draft hypothesis: [drafted hypothesis]. Does this capture your thinking, or would you like to adjust it?"
FILLED: a complete If/Then/Because/Why Now statement

---

### Fields 5–7 — Impact & Metrics (data source first)

**Before Field 5**, run the data-source fork in [impact-analysis.md](impact-analysis.md). Fields 6–7 inherit the same source.

Sub-steps: 5a (data source) → 5b (primary metric) → Field 6 (secondary) → Field 7 (guardrails).

Never invent SQL or baselines. Label every metric with its data source in the final PRD.

---

### Field 5 — Primary Business Metric
[Impact & Metrics · Field 5 of 19]
Context: The North Star metric — the single number that tells you if this feature worked.
See [impact-analysis.md](impact-analysis.md) for the full 5a/5b flow.
Ask (if manual): "What is the single most important metric that will tell you this feature was a success? Include the current baseline and your target if you have them."
Ask (if pre-filled): "Here's what I extracted: [baseline, source, window]. What's your target?"
FILLED: named metric with direction, target, and data source
EMPTY: "improve engagement", metric with no target, numbers without source
Escalation: "What specific number moves if this works — and what does it need to move from and to?"

---

### Field 6 — Secondary Business Metrics
[Impact & Metrics · Field 6 of 19]
Context: Supporting metrics that show the feature is working across multiple dimensions.
Ask: "What secondary metrics will you track alongside the primary one?"
If data was pasted/uploaded, suggest metrics visible in the source. User confirms.
FILLED: 2–3 named secondary metrics
EMPTY: "other metrics", "various KPIs"
Escalation: "Name 2–3 specific metrics you'd check in your dashboard a month after launch."

---

### Field 7 — Guardrail Metrics
[Impact & Metrics · Field 7 of 19]
Context: Guardrails protect against unintended harm — they define what must not get worse.
Ask: "What metrics must not get worse when this ships — what would tell you the feature caused harm even if the primary metric improved?"
FILLED: 1–3 named guardrail metrics with thresholds if available
EMPTY: "nothing", "everything should be fine"
Escalation: "What would you check to make sure you haven't broken something else? What's your rollback trigger?"

---

### Field 8 — Happy Path / Key User Flows
[UX Journey · Field 8 of 19]
Context: Maps the ideal end-to-end user experience when everything works perfectly.
Ask: "Walk me through the happy path — what does the user do, step by step, from entry point to successful completion? Do you have a Figma link for this flow?"
FILLED: step-by-step flow AND/OR a Figma link captured
If no Figma: add placeholder `[Insert Figma link — design to be added before engineering handoff]`
[ASK FOR ASSETS]: "Do you have a Figma link, wireframe, or flow diagram to include?"

---

### Field 9 — Friction Points & Mitigation
[UX Journey · Field 9 of 19]
Context: Identifies where users will struggle and how the design addresses each friction point.
Ask: "Where in the user flow do you expect users to struggle or drop off — and what's the plan to mitigate each friction point?"
FILLED: at least 2 friction points each with a named mitigation
EMPTY: "it should be intuitive", "good UX will handle it"
Escalation: "Imagine a user hitting this for the first time — where do they get confused or stuck?"

---

### Field 10 — Edge Cases
[UX Journey · Field 10 of 19]
Context: Edge cases catch scenarios that break the happy path — catching them here prevents engineering surprises later.
Ask: "What edge cases does this feature need to handle — guest vs logged-in, regional variations, empty states, error conditions?"
FILLED: specific edge cases named across at least 2 categories
EMPTY: "standard edge cases", "engineering will figure it out"
Escalation: "Walk me through 3 scenarios that break the happy path."

---

### Field 11 — Functional Requirements
[Functional Requirements · Field 11 of 19]
Context: The precise behavior the system must exhibit — written so engineering can build acceptance criteria directly from this.
Ask: "Walk me through what this feature must do — the key behaviors, logic, and rules."
After they answer, draft requirements in Given/When/Then format with P0/P1/P2 priority:
- P0: Must-have for launch
- P1: Should-have, important but not blocking
- P2: Nice-to-have, future consideration
Present the draft: "Here are the functional requirements based on what you've described: [drafted]. What's missing, wrong, or needs reprioritizing?"
FILLED: at least 3 P0 requirements validated by user

---

### Field 12 — Non-Functional Requirements
[Functional Requirements · Field 12 of 19]
Context: Performance, security, and accessibility requirements — often overlooked until they become incidents.
Ask: "What are the non-functional requirements — performance targets, security requirements, and accessibility standards?"
FILLED: at least one each of performance, security, and accessibility
EMPTY: "standard requirements"
Escalation: "Name the specific performance threshold, security requirement, and accessibility standard."

---

### Field 13 — Critical Dependencies
[Dependencies · Field 13 of 19]
Context: Surfaces what this feature relies on outside the team's control.
Ask: "For dependencies, you have two options:

Type what you know — describe the systems, APIs, and teams this feature touches.

Run a Cursor scan — I'll generate a prompt you paste into Cursor with your repo open, then paste the output back here and I'll extract the dependencies automatically.

Which would you prefer?"

If user chooses TYPE: accept their answer, ask one follow-up: "Are there any third-party APIs or external services beyond what you've mentioned?"
FILLED: named dependencies with owning team or system. If none: "None identified at this stage" is acceptable.

If user chooses CURSOR SCAN: load the [prd-codebase-scan](../prd-codebase-scan/SKILL.md) skill and run the analysis with the repo open.

When user pastes Cursor output (or scan completes inline):
- Extract all dependencies → pre-fill Field 13
- Extract all technical risks → pre-fill Field 15
- Present both to user for confirmation
- After confirmation, skip Field 15 interview question and move directly to Field 16
- Note in the doc that dependencies and risks were extracted via Cursor codebase analysis

---

### Field 14 — Assumptions
[Assumptions, Risks & Constraints · Field 14 of 19]
Context: Assumptions are conditions the team is treating as true without proof — surfacing them prevents surprises mid-development.
Ask: "What assumptions is this feature built on — business, functional, and technical? What are you treating as true that hasn't been fully validated?"
FILLED: at least one assumption in each category
EMPTY: "no assumptions"
Escalation: "What are you assuming about user behavior, system stability, or business conditions that could turn out to be wrong?"

---

### Field 15 — Risks
[Assumptions, Risks & Constraints · Field 15 of 19]
Context: Risks are things that could go wrong — identifying them now allows mitigation planning before they become incidents.
Ask: "What are the top risks to this feature succeeding — technical, adoption, dependency, or timeline risks?"
FILLED: at least 2 named risks with mitigation
EMPTY: "low risk", "should be fine"
Escalation: "What's the one thing that could make this feature fail — and what's your plan if that happens?"
Note: Skip this field if risks were already extracted from a Cursor scan in Field 13.

---

### Field 16 — Constraints
[Assumptions, Risks & Constraints · Field 16 of 19]
Context: Constraints are fixed boundaries the team must operate within.
Ask: "What are the hard constraints — launch deadlines, platform limitations, regulatory requirements, or budget caps?"
FILLED: at least 1 named constraint with a date or boundary. If none: "No hard constraints identified" is acceptable.

---

### Field 17 — RACXI Table
[Execution & Rollout · Field 17 of 19]
Context: Defines who does what across every phase — prevents accountability gaps during delivery.
Present the RACXI structure:
"Here is the RACXI accountability table. Fill in what you know — leave blank what you don't.

Phases: Discovery / Design / Development / QA / Launch
Roles per phase: R (Responsible) / A (Accountable) / C (Consulted) / X (Approver) / I (Informed)

Who goes in each cell?"

FILLED: user provides at least some names — capture whatever they give, leave rest as [Enter name]

---

### Field 18 — Release Strategy
[Execution & Rollout · Field 18 of 19]
Context: Defines how the feature reaches users — staged rollouts reduce risk and allow course correction before full exposure.
Ask: "Walk me through your release strategy — how does this feature go from internal to full availability? What are the stages, traffic percentages, and success criteria at each gate?"
FILLED: named rollout sequence with stages and criteria
EMPTY: "we'll just ship it"
Escalation: "What's your plan if the canary shows problems — what's the rollback trigger, and who makes that call?"

---

### Field 19 — Stakeholder FAQs
[FAQs · Field 19 of 19]
Context: Anticipates the questions executives, engineers, and PMs will ask — and provides answers before they become blockers.
Ask: "What are the hardest questions stakeholders will ask when you present this PRD? Walk me through the toughest ones and your answers."
FILLED: at least 3 specific Q&A pairs with substantive answers
Escalation: "What's the most likely pushback — 'why now', 'have we validated this', 'what's the rollback plan'? Give me the three hardest ones."
