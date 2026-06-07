# SOW Phase 2 — Baseline (May 2026 onwards, Option 1 Project Based)

Primary compliance scope from May onward. **Ignore Est. Hours.**

## Bucket 1 — CYC / LYB Redesign

| ID | Action item | Priority | Key deliverables |
|----|-------------|----------|------------------|
| 2.1.1 | New CYC/LYB user frontend journey | P0 | Figma recommendations, dev handoff, a11y review |
| 2.1.2 | Landing page build (1 landing page) | P0 | LP desktop+mobile, form setup, SF list, sync QA |

## Bucket 2 — New Lead Gen Form Reporting

| ID | Action item | Priority | Key deliverables |
|----|-------------|----------|------------------|
| 2.2.1 | New lead gen campaign reporting | P1 | Dashboard, SF+HS connections, KPI sign-off |

## Bucket 3 — Airtable Assessment

| ID | Action item | Priority | Key deliverables |
|----|-------------|----------|------------------|
| 2.3.1 | AirTable usage & reporting architecture | P0 | Requirements, architecture doc, base setup |

## Bucket 4 — Attribution (Marketing / Sales)

| ID | Action item | Priority | Blockers / notes |
|----|-------------|----------|------------------|
| 2.4.1 | Create Date property | P0 | MarOps alignment on definition |
| 2.4.2 | Original Source Type | P0 | Audit HS auto-set, no overrides |
| 2.4.3 | First Touch Converting Campaign | P0 | First_Touch_Campaign_Source write-once; Segment/LI/Google/Meta mapping TBD |
| 2.4.4 | First Conversion Date | P1 | Marketing alignment on funnel inclusion |
| 2.4.5 | Last Touch Converting Campaign | P0 | Campaign_Name_v2 fast-track |
| 2.4.6 | Recent Conversion Date | P1 | Marketing alignment |
| 2.4.7 | Date Entered MQL Stage | P0 | HS MQL definition + SF validation |
| 2.4.8 | Number of Unique Forms Submitted | P1 | Custom property + workflow |
| 2.4.9 | Time to MQL | P1 | **Blocked** until Create Date + MQL Date live |
| 2.4.10 | Thomas Lead Score: Engagement Score | P0 | Full audit/rebuild of scoring model |
| 2.4.11 | Thomas Lead Score: Fit Score | P0 | Layer with Engagement Score |
| 2.4.12 | Associated Account Opportunity Lifecycle Stage | P0 | SF→HS sync if missing; Sales hygiene |
| 2.4.13 | Associated Company: Customer Type / Status | P1 | Audit data flow, standardize values |
| 2.4.14 | Opportunity Amount | P1 | SF Amount → HS if missing |
| 2.4.15 | Integration: LinkedIn / Google / Meta / Zoom | P0 | Fix gaps in campaign mapping |
| 2.4.16 | Funnel report build | P0 | **Blocked** until Phase 2 properties complete |
| 2.4.17 | MQL → SQL conversion rate reporting | P1 | Sales SQL definition required |
| 2.4.18 | Lead quality scoring report | P1 | **Blocked** by lead score rebuild |
| 2.4.19 | Automated report distribution | P1 | After report validation |
| 2.4.20 | Multitouch attribution model design (W-shaped) | P0 | **Blocked** until Phases 2+3 data live |
| 2.4.21 | Attribution model implementation | P0 | **Blocked**; may need external tool |
| 2.4.22 | AI agents: attribution intelligence (discovery) | P1 | After Phases 2+3 stable |

## Bucket 5 — Sales Enablement (WIP)

| ID | Action item | Priority |
|----|-------------|----------|
| 2.5.1 | Discovery calls + solution design | P0 |
| 2.5.2 | Plan execution (estimate) | P1 |

## Bucket 6 — Foundation Layer — AI Agents (WIP)

| ID | Action item | Priority | Depends on |
|----|-------------|----------|------------|
| 2.6.1 | AI agents discovery & assessment | TBD | SF, HS, Snowflake schemas |
| 2.6.2 | Sales agent — 1st & last touch insight (POC) | — | First-touch pipeline (1.7) |
| 2.6.3 | Contact & company intelligence agent (POC) | — | Company ID work (1.4) |
| 2.6.4 | Multitouch attribution intelligence (discovery) | — | Attribution fields stable |

## Bucket 7 — Uwa additional tasks (WIP)

| ID | Action item | Priority | Notes |
|----|-------------|----------|-------|
| 2.7.1 | Discovery + architecture roadmap | P0 | |
| 2.7.2 | Plan execution (contact DB cleanup) | P1 | High effort |
