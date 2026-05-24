# GHL Workflows — Build Spec

## Master account workflows

### W1. Demo-form intake
**Trigger:** form submit on nemt-os.ai-loren.com
**Actions:**
1. Create contact
2. Tag: `nemt-demo-request` `src-{utm_source}` `persona-{inferred from fleet_size + biggest_challenge}`
3. Calculate ROI fields (annual recovered revenue, payroll savings)
4. Send internal Slack notification to #nemt-sales
5. Send confirmation email with calendar link + Godspeed case study
6. Add to "NEMT Operators" pipeline → stage 1 (New Demo Request)
7. Wait 5 min → if no calendar booking, send SMS: "Saw you requested a demo — want me to grab a time on your calendar? Reply YES."

### W2. Demo-no-show recovery
**Trigger:** calendar event ended + no attendance flag
**Actions:**
1. Tag: `demo-noshow`
2. Email 1 (immediate): "Missed you — here's the case study and a 1-click rebook link"
3. Email 2 (Day 2): "Still want to see the system? Here's a 90-second Loom"
4. SMS (Day 3): "Wrapping up demo slots this week — want to grab one before Friday?"
5. Email 3 (Day 7): "Last attempt — if not now, when?"
6. If no response by Day 14: tag `nurture-90d`, move to nurture pipeline

### W3. Closed-Won → Onboarding kickoff
**Trigger:** stage moved to "Closed Won" (manual or Stripe webhook)
**Actions:**
1. Tag: `customer-onboarding`
2. Move to "Operator Onboarding" pipeline → stage 1
3. Send kickoff form via email + SMS (collects: logo, colors, current phone number, dispatcher contact, brand voice preference)
4. Notify ops team in Slack #nemt-onboarding
5. Calendar invite for go-live training booked 5–7 days out

### W4. ROI calculator engaged → email capture
**Trigger:** ROI calculator interacted with on site (>3 input changes)
**Actions:**
1. Trigger exit-intent modal: "Get this report by email"
2. On email submit: create contact, tag `roi-calculator-engaged`, send PDF report
3. If no demo booked within 48h: enter 3-email nurture

## Per-client sub-account workflows

### W5. Missed-call text-back
**Trigger:** inbound call missed (no answer in 3 rings OR voicemail)
**Actions:** auto-SMS within 60s: "Hi, this is {OPERATOR_NAME}. Saw your call. What do you need help with? Reply here and we'll handle it."

### W6. New ride booked (via Grace or form)
**Trigger:** ride_status set to `booked`
**Actions:**
1. SMS confirmation to patient
2. Email confirmation to patient (if email on file)
3. Calendar event created in dispatcher view
4. Pipeline opportunity created at "Booked"
5. Tag patient `ride-booked`
6. Notify dispatcher channel
7. Schedule 24h reminder (W7) and 2h reminder (W8)

### W7. 24h reminder
**Trigger:** 24h before pickup_datetime
**Actions:** SMS "Reminder: pickup tomorrow at {time} from {pickup_address}. Reply C to confirm, X to cancel."

### W8. 2h pre-pickup
**Trigger:** 2h before pickup_datetime
**Actions:** SMS "Your ride with {driver_name} ({vehicle_make} {vehicle_color}) will arrive at {eta}. Reply HELP to speak with us."

### W9. No-show recovery
**Trigger:** ride_status set to `no-show`
**Actions:**
1. Wait 30 min
2. Trigger Grace outbound call (W9.1): "We missed you — want to rebook?"
3. If rebooked: tag `no-show-recovered`
4. If not: tag `no-show-unrecovered`, notify dispatcher

### W10. NPS request (24h after completed ride)
**Trigger:** ride_status set to `completed` + 24h delay
**Actions:** SMS "How was your ride? Reply 1–5."
Branching: 4–5 → Google review request; 1–3 → owner alert

### W11. Stale-customer reactivation (90 days)
**Trigger:** patient last_ride_date > 90 days AND NOT tagged `opted-out`
**Actions:** 3-email + 1-SMS sequence per `prompts/followup-reactivation.md`

### W12. Owner daily brief (8 AM operator timezone)
**Trigger:** daily 8 AM cron
**Actions:**
1. Pull yesterday's metrics
2. Run through Claude API for natural-language summary
3. Send SMS + email: "Yesterday: {calls} answered · {rides} booked · {recovered} recovered · ${captured}. {alerts}"

### W13. Weekly KPI report (Monday 7 AM)
**Trigger:** Monday 7 AM cron
**Actions:** generate PDF + dashboard link, email to owner

### W14. Facility weekly check-in (Mondays 9 AM)
**Trigger:** Monday 9 AM, for each contact tagged `caller-facility` + `customer-live`
**Actions:** email this-week schedule confirmation per `prompts/followup-reactivation.md` part C
