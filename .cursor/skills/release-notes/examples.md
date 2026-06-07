# Examples

## Raw Input (technical — do not mirror in output)

Building on the Gatsby → Next.js migration completed in Phase 1, Phase 2 injected three targeted CTAs onto 5 Xometry resources pages, focused on driving email capture from high-intent organic visitors. The rollout followed a low-risk canary approach (cookie override → 1% → 10% → 100%), with a dedicated measurement plan.

---

## Extract + Gate (launch and metrics missing)

I found: email capture CTAs on resources pages; staged rollout mechanics (no final % or date).

I still need:
- **Launch date / rollout status:** When did this ship, and what % of users is it live to?
- **Impact metrics:** Share directly, paste a dashboard export, or point to Snowflake. Or reply **"No impact metrics"**.
- **PRD link** (required before I finalize)

---

## Company-Wide — 7 Lines (gold standard)

Reorder is now one click from Order History and order confirmation.
Buyers placing repeat orders can repurchase without rebuilding a cart.
The button appears on Order History, the dashboard orders tab, and confirmation pages.
It went live March 12 to 100% of traffic outside the buyer portal.
The A/B test showed +49% clicks and +37% orders; finance estimated $10.5M incremental bookings annually (per provided analysis).
22% of clickers used Reorder more than once in the first month.
[BXP-1155](https://xometry.atlassian.net/browse/BXP-1155) – [PRD](https://confluence.example.com/prd/reorder)

Note: $ figure only because user/finance provided it. "Statistically significant" omitted unless user stated it.

---

## Company-Wide — No Impact Metrics

Saved payment methods now persist when buyers navigate away from checkout and return.
Checkout users no longer need to re-enter billing details on every visit.
The change applies to the standard checkout flow on xometry.com.
It went live April 2 to 100% of checkout traffic.
Buyers complete checkout faster when returning to an in-progress order (no metric provided).
This removes a common friction point for repeat purchasers at the payment step.
– [PRD](https://confluence.example.com/prd/checkout-billing)

Line 5 uses no invented metric — line 6 carries outcome without fake numbers. No ticket (optional).

---

## Customer-Facing — 7 Lines

You can now reorder past purchases with one click from your order history.
Returning customers save time by skipping cart rebuilds for parts they've bought before.
The Reorder button appears on order history, your dashboard, and order confirmation pages.
It is available to all customers on xometry.com as of March 12.
Repeat buyers are adopting it quickly based on early usage data we measured before full launch (+37% reorder actions in the test period).
This makes repeat sourcing faster for teams that order the same parts regularly.
– [PRD](https://help.xometry.com/reorder)

No Jira link. Rollout in customer language. Metrics only as user provided.

---

## Anti-Patterns

| Bad | Why |
|-----|-----|
| "+37% orders → $10.5M" without user providing $ | Invented extrapolation |
| "Statistically significant lift" without proof | Overclaim |
| "Improves checkout performance" with no metrics | Qualitative filler |
| 8 lines or bullet list | Format violation |
| Full newsletter with intro | Slot only |
| Output without PRD link | PRD required |
