# Automation — Appointment / Ride Booking

## Goal
Take a captured ride intent (from Grace or form) and turn it into a confirmed dispatch-ready ride within 2 minutes.

## Flow
```
Ride intent captured
       │
       ▼
Validate:
  - pickup address in service area? (zip check)
  - pickup datetime ≥ 2h from now? (or stretcher: ≥ 4h)
  - mobility type captured?
  - broker / payment source captured?
       │
       ▼
If valid:
  - Create contact (or merge with existing)
  - Create ride opportunity at "Booked" stage
  - Generate ride_id
  - Send confirmation SMS + email
  - Schedule 24h + 2h reminders
  - Notify dispatcher
  - Add to driver app queue (auto-assign if rules match)

If invalid (missing data or out of service area):
  - Grace re-prompts caller for missing data
  - If still invalid: escalate to dispatcher with notes
```

## Auto-assign rules (in priority order)
1. Driver currently assigned to this patient's standing order
2. Driver in geographic proximity to pickup address
3. Driver with right vehicle type for mobility need
4. Driver with capacity in the time window
5. Round-robin if multiple drivers tie
