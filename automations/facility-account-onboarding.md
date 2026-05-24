# Automation — Facility Account Onboarding

## Goal
Convert a single facility-coordinator call into a recurring B2B account that books 20–60 rides/week.

## Trigger
Grace identifies caller as facility coordinator (nursing home, dialysis, SNF, behavioral health, etc.) → `caller-facility` tag.

## Flow

```
Facility-coordinator call captured
       │
       ▼
Grace captures: facility name, coordinator name, coordinator email, facility address, typical ride volume, mobility mix
       │
       ▼
Create Facility entity in GHL → stage 1 (Discovery)
       │
       ▼
Send welcome email to coordinator:
  - Facility-account portal access
  - Bulk-ride request form link
  - Direct phone line / SMS shortcut
  - Pricing memo for facility accounts (if applicable)
       │
       ▼
Notify owner: "New facility account opportunity — {FACILITY_NAME}"
       │
       ▼
Monday auto-emails: weekly schedule confirmation per /prompts/followup-reactivation.md part C
       │
       ▼
At 4 weeks of active use → stage to "Active"
At <50% expected volume → stage to "At Risk" + alert owner
At 60 days no bookings → stage to "Churned"
```

## Facility-account upsells (sold in QBR)
- Dedicated phone tree extension just for the facility
- White-label SMS sender name matching the facility
- Weekly auto-generated facility billing summary
- Custom rate sheet for high-volume facilities
