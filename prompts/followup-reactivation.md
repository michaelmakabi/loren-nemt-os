# Prompt — Follow-up + Reactivation Sequences

## A. Post-ride follow-up (24h after completed ride)

**SMS:**
> Hi {first_name}, this is {OPERATOR_NAME}. How was your ride with us yesterday? Reply 1–5 (5 = perfect). Anything we should know? — Grace

**Branching:**
- Reply 4 or 5 → thank-you SMS + Google review request
- Reply 1–3 → escalate to owner, owner calls within 24h
- No reply → no further action; tagged `nps-no-response`

## B. Stale-customer reactivation (no rides booked in 90 days)

**Email 1 (Day 0):**
Subject: We've missed you — quick scheduling check

> Hi {first_name},
> It's been a while since we last gave you a ride. We hope everything's well.
> If you have any upcoming appointments — dialysis, doctor, therapy — we're here. Reply to this email or text us at {OPERATOR_PHONE} and we'll book it in under 2 minutes.
> — {OPERATOR_OWNER_NAME}, Owner
> {OPERATOR_NAME}

**Email 2 (Day 5):**
Subject: A quicker way to book your rides

> Hi {first_name},
> Quick heads up — we've made booking easier. You can now text us at {OPERATOR_PHONE} 24/7 and we'll handle the rest. No phone tag.
> Have a ride coming up? Just text us the day and time.
> — {OPERATOR_NAME}

**SMS (Day 10):**
> {first_name}, it's {OPERATOR_NAME}. We've moved 1,200+ patients since you last booked. Whenever you need a ride, just text this number. — Grace

**Email 3 (Day 15):**
Subject: One last thing

> Hi {first_name},
> If we're not the right fit anymore, no hard feelings — reply STOP and we'll take you off our list.
> Otherwise, we're here whenever you need us.
> — {OPERATOR_NAME}

## C. Facility-account weekly check-in (Mondays, 9 AM)

**Email to facility coordinator:**
Subject: This week's transportation schedule confirmation

> Hi {coordinator_name},
> Here's what we have on the books for {facility_name} this week:
> - Mon: {monday_count} rides
> - Tue: {tuesday_count} rides
> - Wed: {wednesday_count} rides
> - Thu: {thursday_count} rides
> - Fri: {friday_count} rides
>
> Any additions, cancellations, or changes? Reply here or text {OPERATOR_PHONE}.
> — {OPERATOR_NAME}

## D. No-show recovery (within 30 min of no-show)

**Grace places a call:**
> "Hi {first_name}, this is Grace at {OPERATOR_NAME}. Our driver was at {pickup_address} at {pickup_time} and we weren't able to make contact. Are you still needing transportation today? I can rebook you for {next_available_slot}."

Then logs:
- contact tag: `no-show-recovered` (if rebooked) or `no-show-unrecovered` (if not)
- pipeline note
