# Automation — Missed-Call Text-Back

## Goal
Convert every missed call into a captured conversation within 60 seconds.

## Trigger
Inbound call to operator's Retell-routed number that:
- Drops to voicemail, OR
- Is not picked up in <3 rings, OR
- Is picked up but caller hangs up before identifying intent

## Flow

```
Missed call event
       │
       ▼
Wait 30s
       │
       ▼
Send SMS to caller:
"Hi, this is {OPERATOR_NAME}. Saw your call — what do you need help with?
 Reply here and we'll handle it. — Grace"
       │
       ▼
If reply within 5 min:
  → escalate text into a Retell conversation (or human dispatcher channel)
  → tag contact: missed-call-recovered
       │
If no reply within 60 min:
  → second SMS: "Just checking back — you can also book a ride at {OPERATOR_BOOKING_URL}."
  → tag contact: missed-call-no-recovery
```

## KPIs
- Missed-call → SMS-reply rate (target: 35%+)
- SMS-reply → booked-ride rate (target: 50%+)
- Net captured rate (missed → booked) (target: 17%+)
