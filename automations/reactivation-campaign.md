# Automation — Stale Customer Reactivation

## Goal
Recover 10–20% of customers who haven't booked in 90 days.

## Trigger
Contact with no `ride-booked` event in 90 days AND not tagged `opted-out`.

## Sequence
Day 0: Email 1 (warm check-in)
Day 5: Email 2 (easier-to-book reminder)
Day 10: SMS (low-friction nudge)
Day 15: Email 3 (graceful exit option)

See full copy in `prompts/followup-reactivation.md` part B.

## Stop conditions
- Customer books a ride → tag `reactivated`
- Customer replies STOP → tag `opted-out`
- Customer replies negatively → tag `do-not-contact`
- Hard bounce → mark email invalid

## KPIs
- Reactivation rate (booked within 21 days): target 12%+
- Opt-out rate: keep <3%
- ROI per reactivated customer: avg lifetime $480 vs $0 reach-out cost
