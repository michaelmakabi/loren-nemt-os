# GHL Pipelines & Stages

## Pipeline 1 — "NEMT Operators" (Loren AI's master account, sales pipeline)

| Stage | Definition | Auto-move trigger |
|---|---|---|
| 1. New Demo Request | Form submitted on nemt-os.ai-loren.com | Form submit |
| 2. Demo Booked | Calendar event created | Calendar booking |
| 3. Demo Showed | Operator attended the call | Manual / Zoom webhook |
| 4. ROI Sent | Custom ROI report delivered | Manual / template send |
| 5. Proposal Sent | Stripe checkout link sent | Stripe link generated |
| 6. Negotiation | Operator pushing back on price/terms | Manual |
| 7. Closed Won | Stripe checkout completed | Stripe paid webhook |
| 8. Closed Lost | Operator declined | Manual |
| 9. Nurture (90-day revisit) | Not now but worth re-touch | Manual |

## Pipeline 2 — "Operator Onboarding" (Loren AI's master account, post-sale)

| Stage | Definition | SLA |
|---|---|---|
| 1. Kickoff Form Sent | Onboarding form auto-sent on close | <5 min |
| 2. Kickoff Form Completed | Operator submitted brand assets + phone forwarding info | <24h |
| 3. Subdomain Provisioned | GoDaddy A record live | <1h |
| 4. Lovable Project Cloned + Branded | White-label deployed | <12h |
| 5. GHL Sub-Account Built | Snapshot imported | <6h |
| 6. Retell Agent Live | Phone tested with internal calls | <12h |
| 7. Operator Training Booked | Calendar invite sent | <24h |
| 8. Go-Live | Phone number routed, system live | <72h total |
| 9. 14-Day Check-in | First QBR loom sent | Day 14 |
| 10. Steady State | Monthly QBR cadence | Recurring |

## Pipeline 3 — Per-client "Ride Lifecycle" (in each operator's sub-account)

| Stage | Definition |
|---|---|
| 1. Inbound Inquiry | Caller / form / facility submission, no ride yet |
| 2. Quoted | Ride priced and offered |
| 3. Booked | Ride confirmed |
| 4. Reminded (24h) | 24h reminder sent |
| 5. Reminded (2h) | 2h reminder sent |
| 6. En Route | Driver picked up |
| 7. Completed | Ride finished |
| 8. No-Show | Driver arrived, rider absent |
| 9. Cancelled | Cancelled by rider or facility |
| 10. Recovered | No-show or cancel rebooked successfully |
| 11. Reviewed | NPS captured |

## Pipeline 4 — Per-client "Facility Account" (in each operator's sub-account)

| Stage | Definition |
|---|---|
| 1. Discovery | Initial outreach to facility |
| 2. Onboarding | Facility coordinator set up with portal access |
| 3. Active | Regular bookings happening |
| 4. At Risk | <50% of expected weekly volume |
| 5. Churned | No bookings in 60 days |
