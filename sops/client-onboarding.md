# Client Onboarding SOP — <72hr SLA

## Hour 0 — Close

- Stripe checkout completed → webhook → GHL Closed-Won
- Kickoff form auto-sent (collects logo, color, current phone, dispatcher contact, voice preference, service area, broker mix)

## Hour 0–6 — Kit assembly (parallel)

| Task | Owner | Duration |
|---|---|---|
| Subdomain provision via GoDaddy API | Ops | 15 min |
| Lovable project clone + white-label theming | Ops | 3 hr |
| Favicon + OG asset creation | Ops | 1 hr |
| GHL sub-account from snapshot | Ops | 30 min |
| Inject custom field values from kickoff form | Ops | 15 min |
| Stripe customer record + invoice | Ops | 10 min |

## Hour 6–24 — Voice + telephony

| Task | Duration |
|---|---|
| Retell agent created from Grace template | 30 min |
| Operator variables injected | 15 min |
| ElevenLabs voice selected (Grace default) | 5 min |
| Phone number provisioned in Retell | 15 min |
| Test call pack — 5 scenarios run | 1 hr |

## Hour 24–48 — Integration

| Task | Duration |
|---|---|
| GHL ↔ Retell webhooks configured | 30 min |
| Stripe webhook configured (operator's billing of their customers, if applicable) | 15 min |
| Operator's existing customer list imported | 1 hr |
| Test end-to-end: inbound call → ride booked → dashboard updated | 1 hr |

## Hour 48–72 — Cut-over

| Task | Duration |
|---|---|
| Lovable badge confirmed hidden | 5 min |
| Final brand-pass | 15 min |
| Operator's existing phone number forwarded to Retell number | 30 min (varies by carrier) |
| Go-live training call with operator + dispatcher | 60 min |
| Mark "Go-Live" in pipeline | 1 min |

## Day 7 — First QBR Loom

Send 5-minute Loom recap:
- Calls answered
- Rides booked
- Recovered missed calls
- Captured revenue
- Anything noteworthy

## Day 14 — Steady-state cadence begins

Daily owner brief, weekly KPI report, monthly QBR.

## Test call pack (5 scripted scenarios)

1. New ride request — wheelchair-accessible van, dialysis center pickup tomorrow 7 AM
2. Status check — caller asks "where's my ride?"
3. Facility bulk — nursing home coordinator booking 3 residents for SNF transfer
4. Cancellation + reschedule — patient cancels tomorrow, books Friday
5. Edge case — after-hours emergency at 11 PM for next-day 6 AM dialysis

All 5 must pass before go-live.
