# Interview Fields — 17 Fields + FAQ

Run [evidence-analysis.md](evidence-analysis.md) after ENTRY, before Field 3.

### Field 1 — WHO is affected
[Problem Statement · Field 1 of 17]
Context: Identifies the specific customer or user group at the center of this business problem.
Ask: "Who specifically experiences this problem — which customer type, supplier segment, or user role, and roughly how many accounts or users are we talking about?"
FILLED: named segment + scale ("mid-market manufacturing suppliers, ~300 active accounts")
EMPTY: "customers", "users", "suppliers" with no qualification
Escalation: "Can you be more specific — which tier, vertical, or account type? And roughly how many — tens, hundreds, thousands of accounts?"

---

### Field 2 — WHAT breaks today
[Problem Statement · Field 2 of 17]
Context: Defines the specific failure point — the precise moment where the experience breaks down.
Ask: "Describe exactly what happens when this problem occurs — walk me through the specific failure step by step, in operational terms. What does the customer or your team actually experience?"
FILLED: a concrete failure sequence with enough detail a stakeholder could picture it
EMPTY: a solution description ("we need to build X"), a category label, or a single sentence with no operational detail
Escalation: "What does that look like in practice — what's the exact moment things go wrong? Walk me through a real example from start to failure."

---

### Field 3 — Measurable outcome
[Problem Statement · Field 3 of 17]
Context: Quantifies the problem's impact — the number that proves this is worth solving.
If Snowflake or other tool pre-filled data, confirm: "Here's what I extracted: [number, source, window]. Does this match your understanding?"
Ask (if manual): "What is the measurable impact of this problem today — put a number on it. Even a rough estimate: percentage of cases affected, revenue at risk per month, hours lost per week, complaints per quarter."
FILLED: any specific number or honest range with data source labeled
EMPTY: "significant", "meaningful", "a lot", numbers without source
Escalation A: "When you say [their phrase] — can you put a number on it? Even order of magnitude: are we talking $10K or $1M at risk?"
Escalation B: "Who in your org would have the closest number — a data analyst, finance, ops? Could you get even a rough figure?"
[ASK FOR CHARTS]: "Do you have any data exports, dashboards, or charts showing this impact? Upload or share a link and I'll reference it."

---

### Field 4 — Evidence
[Problem Statement · Field 4 of 17]
Context: Establishes the credibility of the problem — executives will ask 'how do we know this is real?'
Ask: "What evidence do you have that this problem is real and significant — analytics data, support tickets, sales escalations, audit findings, customer quotes, lost deals?"

If FullStory/Conviva/Snowflake connected, offer to pull supporting evidence for the failure described in Field 2.

Classify into evidence tiers (internal — do not show menu to user):
- Tier 1: Hard data — Snowflake, analytics exports, A/B results
- Tier 2: Research — FullStory sessions, user interviews, surveys
- Tier 3: Proxy — support tickets, sales escalations, audit findings, NPS
- Tier 4: Hypothesis — internal assumption, not yet validated

Tell user: "Based on what you've shared, this is Tier [X] evidence — [one line on what would strengthen it]."

If Tier 4 — mandatory 3-step sequence before FILLED:
1. "What exactly is the hypothesis — describe in detail what you believe is happening and why."
2. "What triggered this belief — was there a specific incident, customer complaint, or data point?"
3. "What's the fastest way to validate it — who could pull data or run a query to confirm?"
Only after all three does Field 4 count as FILLED.

[ASK FOR CHARTS]: "Do you have any supporting data, screenshots, or reports to include?"

---

### Field 5 — Business impact
[Impact & Scope · Field 5 of 17]
Context: Connects the problem to business consequences — the 'so what' for executive stakeholders.
If data pre-filled, confirm with user before proceeding.
Ask: "If this problem goes unsolved for another year, what specifically happens to the business — which metric takes the hit, and by roughly how much?"
FILLED: a specific consequence with a number and source
EMPTY: directional language with no number
Escalation A: "Can you quantify that — revenue at risk, customer count at risk, or cost of the current manual workaround?"
Escalation B: "Even directional: is this a $50K problem or a $500K problem annually?"
[ASK FOR CHARTS]: "Do you have any trend data or financial reports showing this impact over time?"

---

### Field 6 — Competitive context
[Market & Opportunity · Field 6 of 17]
Context: Shows whether competitors have solved this and what that means for your position.
Ask: "Do competitors handle this better today — and if so, what does that mean for the risk of not acting? Have customers or sales ever raised competitors in the context of this problem?"
FILLED: competitors named with specific detail, or explicitly confirmed as not applicable with reasoning
EMPTY: "probably" / "maybe" / silence
Escalation: "Even if you don't know specifics — do customers ever mention other platforms when raising this issue?"

---

### Field 7 — Market growth & timing
[Market & Opportunity · Field 7 of 17]
Context: Explains why solving this now compounds returns — and why delay compounds risk.
Ask: "Is there a market or growth dynamic that makes solving this more valuable now than in 12 months — more users onboarding, growing volume, scaling complexity?"
FILLED: a specific growth factor with context
If not applicable: "Not applicable" with a brief reason is acceptable

---

### Field 8 — Current state detail
[Current State · Field 8 of 17]
Context: Gives stakeholders a concrete picture of what broken looks like today.
If FullStory connected, offer: "I can pull session events for a specific user or session to illustrate this — do you have a session ID or user to investigate?"
Ask: "Walk me through a specific real example of this problem happening — what does a user or your team actually experience, step by step, including the workaround?"
FILLED: a specific scenario with operational detail; source labeled if from FullStory
EMPTY: repeat of Field 2 with no added detail
Escalation: "Give me one concrete case — even with approximate numbers. What went wrong, what did it cost, and what did someone have to do to fix it manually?"
Then: "Do you have any supporting material — a customer email, a ticket, a screenshot?"

---

### Field 9 — Desired business outcome
[Desired Outcome · Field 9 of 17]
Context: Defines what success looks like in business terms — outcome executives approve, not the feature built.
Ask: "If this is solved perfectly, what does the business look like in 12 months — which specific metric has moved, from what baseline to what target?"
FILLED: specific business outcome with metric and direction
EMPTY: feature description, vague improvement language
Escalation: "Which number specifically improves — frame it as: X goes from [current] to [target] within [timeframe]."

---

### Field 10 — Urgency driver
[Why Now · Field 10 of 17]
Context: Explains the forcing function — why this quarter rather than later.
Ask: "What is making this urgent right now — what's the specific forcing function?"
FILLED: specific named reason with context
EMPTY: "it's important", "leadership wants it"
Escalation: "Name the specific thing that makes this quarter different from next quarter."

---

### Field 11 — Financial impact
[Business Impact · Field 11 of 17]
Context: The financial case — the number that justifies the investment.
If Snowflake pre-filled, confirm with user.
Ask: "What is your best estimate of the financial impact — revenue at risk, cost savings, or margin recovery — and how did you arrive at that number?"
FILLED: number or range with reasoning and source
EMPTY: "significant", "meaningful ROI"
Escalation A: "Let's build a rough number — affected customers × contract value × expected % improvement?"
Escalation B: "Even directional: $50K opportunity or $500K?"
[ASK FOR CHARTS]: "Do you have a financial model or projection spreadsheet to include?"

---

### Field 12 — Financial category
[Business Impact · Field 12 of 17]
Context: Frames the financial story for the right executive lens.
Ask: "How would you categorize the primary financial story — Revenue Growth, Cost Reduction, Risk Mitigation, Customer Retention, or Market Expansion? It can be more than one."
FILLED: one or more categories named

---

### Field 13 — OKR / Strategic link
[Approval Context · Field 13 of 17]
Context: Connects this initiative to company priorities — critical for executive sign-off.
Ask: "Which company or team OKR does this connect to — can you name it or paste a link?"
FILLED: OKR name, number, or link — or "not linked to a current OKR" with reason

---

### Field 14 — Target timeline
[Approval Context · Field 14 of 17]
Context: Sets stakeholder expectations on when this will be resolved.
Ask: "What is the target delivery quarter or deadline for this initiative?"
FILLED: quarter, date, or "not yet defined"

---

### Field 15 — Business owner
[Approval Context · Field 15 of 17]
Context: Every BRD needs a named owner before executives will approve.
Ask: "Who owns this initiative — name and department?"
FILLED: name or team
If "TBD": "I need this before generating — even an interim owner works."

---

### Field 16 — Teams involved
[Approval Context · Field 16 of 17]
Context: Maps cross-functional dependencies executives need to know about.
Ask: "Which teams are involved in delivering this initiative?"
FILLED: named teams
Never offer options — you do not know their org structure

---

### Field 17 — Budget requested
[Approval Context · Field 17 of 17]
Context: Investment figure finance and executives need to approve.
Ask: "Is there a budget figure allocated or requested — even a rough range?"
FILLED: number, range, or explicit "none" / "TBD"
Never drop the row — write "None requested" or "[To be confirmed]"

---

### Field FAQ — Stakeholder objections
[FAQs · Final field]
Context: Anticipates hardest executive questions.
Ask: "What objections do you expect from CTO or executive leadership — and what is your answer to each?"
FILLED: at least 3 specific Q&A pairs with substantive answers
Escalation: "What's the most likely pushback — 'why now', 'do we have the data', 'is this worth the engineering cost', 'what's the ROI'?"
