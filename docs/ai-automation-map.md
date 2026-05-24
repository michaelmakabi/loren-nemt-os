# AI Automation Map

## The 12 automations Loren AI ships per operator

### 1. Inbound Call → AI Receptionist (Grace)
- **Trigger:** any inbound to the operator's assigned phone number.
- **Engine:** Retell AI + ElevenLabs voice (Grace, NEMT-trained).
- **Actions:** greet → identify caller type → branch (new ride / status / facility / driver / cancellation / after-hours).
- **Output:** call summary → GHL contact note → optional ride request → optional dispatcher escalation.

### 2. Missed-Call Text-Back
- **Trigger:** any inbound that drops to voicemail OR is not picked up in <3 rings.
- **Engine:** GHL Workflow.
- **Action:** auto-SMS within 60s: "Hi, this is {Operator} — saw your call. What do you need help with? Reply here and we'll handle it."

### 3. Lead Qualification → Pipeline Auto-Move
- **Trigger:** new contact created from Grace OR booking form.
- **Engine:** GHL workflow + custom JS for scoring.
- **Action:** score on (a) caller intent (new ride > status > complaint), (b) facility account flag, (c) ride value. Move into pipeline stage based on score.

### 4. Appointment / Ride Booking Confirmation
- **Trigger:** ride booked (via Grace or form).
- **Engine:** GHL.
- **Action:** confirmation SMS + email to caller, calendar event created, dispatcher notified.

### 5. 24hr Ride Reminder
- **Trigger:** 24h before scheduled pickup.
- **Engine:** GHL workflow.
- **Action:** SMS reminder. Reply "C" to confirm, "X" to cancel. Auto-rebook flow on cancel.

### 6. 2hr Pre-Pickup Reminder
- **Trigger:** 2h before scheduled pickup.
- **Engine:** GHL workflow + Twilio.
- **Action:** SMS with driver name + ETA + vehicle make/color.

### 7. Driver-Side Status Updates
- **Trigger:** driver marks "en route" / "arrived" / "picked up" / "completed".
- **Engine:** GHL form/webhook from driver app.
- **Action:** customer auto-SMS at each stage. Dashboard timeline updated.

### 8. No-Show Recovery
- **Trigger:** driver marks "no-show".
- **Engine:** GHL workflow.
- **Action:** AI call back 30 min later to rebook. Tag contact `no-show-recoverable`.

### 9. Stale-Lead Reactivation Campaign
- **Trigger:** contact inactive 90 days.
- **Engine:** GHL workflow.
- **Action:** 3-email + 1-SMS reactivation series. "We've moved 1,200 patients since you last booked — want to schedule again?"

### 10. Facility-Account Bulk Booking
- **Trigger:** facility-account contact submits bulk-ride form OR Grace handles a facility call.
- **Engine:** GHL + custom code (CSV parse).
- **Action:** parse N rides from one request, create N pipeline opportunities, dispatcher confirms in one click.

### 11. Owner Daily Brief (8 AM)
- **Trigger:** daily 8 AM, operator's timezone.
- **Engine:** GHL workflow + Loom-style AI summary (Claude API).
- **Action:** SMS/email: "Yesterday: 247 calls answered · 183 rides booked · 34 recovered · $2,890 captured · 0 incidents. 2 things need your attention: [list]."

### 12. Weekly KPI Report (Monday 7 AM)
- **Trigger:** Monday 7 AM.
- **Action:** PDF + dashboard link emailed: rides booked, revenue captured, driver utilization, no-show rate, top facility accounts, week-over-week delta.

## Cross-cutting AI services

| Service | Provider | Used by |
|---|---|---|
| Voice AI | Retell AI | #1, #8 |
| Voice synthesis | ElevenLabs | #1, #8 |
| NLU / intent | Retell built-in + Claude fallback | #1, #3 |
| LLM summaries | Claude API | #1 (call summaries), #11 (daily brief) |
| Workflow engine | GoHighLevel | #2–#12 |
| SMS / email | GHL + Twilio | All |
| Payments | Stripe | Operator subscription (not customer rides yet) |
| Storage | GHL native | All |

## Future automations (post-PMF)

- **#13. Broker EDI bridge** — auto-sync rides with MTM/Modivcare/Verida.
- **#14. Insurance claim packet generator** — auto-build CMS-required documentation per ride.
- **#15. Driver-supply marketplace** — borrow a vehicle from a partner operator when over capacity.
- **#16. AI dispatcher copilot** — chat surface in admin dashboard that can answer "show me all unassigned dialysis rides for Tuesday".
