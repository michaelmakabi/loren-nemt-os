# GHL Tags & Segments

## Master account (sales) — tags

### Source tags
- `src-cold-email` `src-linkedin` `src-organic` `src-referral` `src-conference` `src-paid-ad`

### Engagement tags
- `nemt-demo-request` `roi-calculator-engaged` `compound-calc-engaged` `case-study-viewed`
- `demo-booked` `demo-showed` `demo-noshow` `demo-rescheduled`
- `proposal-sent` `proposal-opened`

### Lifecycle tags
- `closed-won` `closed-lost` `nurture-90d` `dead-lead`
- `customer-onboarding` `customer-live` `customer-at-risk` `customer-churned`

### Persona tags (auto-assigned via form fields)
- `persona-otis` `persona-olivia` `persona-eric` `persona-unknown`

### Tier tags
- `tier-founder` `tier-growth` `tier-fleet`

## Per-client account (operations) — tags

### Caller-type tags
- `caller-patient` `caller-facility` `caller-broker` `caller-driver` `caller-vendor` `caller-wrong-number`

### Ride-state tags
- `ride-booked` `ride-completed` `ride-cancelled` `ride-noshow`
- `no-show-recoverable` `no-show-recovered` `no-show-unrecovered`

### Mobility tags
- `mobility-ambulatory` `mobility-wheelchair` `mobility-stretcher` `mobility-bariatric`

### Broker tags
- `broker-mtm` `broker-modivcare` `broker-verida` `broker-access2care` `broker-saferide` `broker-private-pay` `broker-medicare-advantage`

### Facility tags
- `facility-dialysis` `facility-snf` `facility-behavioral` `facility-oncology` `facility-methadone`

### Engagement tags
- `nps-promoter` `nps-passive` `nps-detractor` `nps-no-response`
- `stale-30d` `stale-60d` `stale-90d` `reactivated`

## Standard segments (auto-built from tag combinations)

| Segment | Definition |
|---|---|
| Hot demo pipeline | `demo-booked` AND NOT `closed-won` AND NOT `closed-lost` |
| At-risk demos | `demo-noshow` AND <14 days old |
| Re-engagement queue | `nurture-90d` AND last_activity > 60d |
| Facility weekly check-in | `caller-facility` AND `customer-live` (all facility accounts) |
| No-show recovery queue | `no-show-recoverable` AND <24h old |
| Reactivation candidates | `stale-90d` AND NOT `reactivated` AND NOT opted_out |
