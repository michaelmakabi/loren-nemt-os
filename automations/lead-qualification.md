# Automation — Lead Qualification

## Goal
Auto-classify every new lead (patient, facility, broker, vendor) and route into the right pipeline / stage / cadence within 30 seconds.

## Inputs
- Grace call summary (`caller_type`, `intent`)
- Form submission fields (if applicable)
- Phone number lookup (existing contact? facility account?)

## Scoring rubric
| Signal | Weight |
|---|---|
| Caller is facility coordinator | +30 |
| Caller mentions specific broker name | +20 |
| Intent = book new ride | +25 |
| Intent = status check | +10 |
| Caller is repeat (within 90 days) | +15 |
| Mobility = wheelchair / stretcher | +10 (higher ride value) |
| Caller is angry / complaint | -20 (route to owner, not pipeline) |
| Caller mentions Medicaid | +15 |
| Caller is wrong number | -100 (drop) |

Score → routing:
- 50+: hot pipeline, dispatcher notification
- 25–49: warm pipeline, no immediate notification
- 0–24: cold tag, follow up later
- Negative: escalation or drop
