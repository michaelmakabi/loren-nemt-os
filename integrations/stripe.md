# Stripe — Billing Runbook

## Products

| Product | Price ID label | Monthly | Setup (one-time) |
|---|---|---|---|
| Founder | `loren_nemt_founder_monthly` | $1,997 | $2,500 |
| Growth | `loren_nemt_growth_monthly` | $3,497 | $4,500 |
| Fleet | `loren_nemt_fleet_monthly` | $6,997 | $9,500 |

## Add-ons (recurring)
- Additional phone number — $200/mo
- Additional voice (e.g., Spanish) — $400/mo
- White-label driver app (native) — $1,500/mo

## Add-ons (one-time / custom)
- Broker EDI integration — custom quote
- Workflow engineering hours beyond plan — $250/hr

## Flow at close
1. Salesperson generates Stripe checkout link from Closed-Won GHL automation.
2. Link emailed + SMS'd to operator.
3. On Stripe paid webhook → GHL stage moves to Onboarding pipeline → kickoff form sent.
4. Setup fee invoiced immediately, MRR begins on go-live (auto-set 7 days out).

## Annual prepay incentive
- 12-month prepay = 2 months free (10x MRR + $1 add-on number free for 12mo)
- 24-month prepay = 5 months free, setup waived

## Failed-payment handling
- Day 1: GHL auto-SMS + email "card declined — quick fix"
- Day 3: phone call from CS
- Day 7: services paused (dashboard + voice still up, but no new feature deploys)
- Day 14: hard pause (forward calls back to operator), 30-day clock to cancel

## Refund / guarantee invocation
- 60-day capture guarantee: refund setup fee if <3 captured rides/day measured average over first 60 days
- Process: operator emails ops@ai-loren.com → audit logs verified → refund processed within 5 business days
