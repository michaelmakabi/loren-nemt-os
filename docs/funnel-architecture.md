# Funnel Architecture

## Top-line funnel

```
COLD AWARENESS                  ──►  LANDING PAGE (nemt-os.ai-loren.com)
   ├── Cold email (Instantly)         ├── Hero · pain frame
   ├── LinkedIn outbound              ├── Hidden-leak section
   ├── Conference / referrals         ├── ROI calculator (interactive)
   └── Organic search                 ├── Human-vs-AI table
                                      ├── Platform overview (7 features)
                                      ├── Godspeed case study
                                      ├── Call demo audio (8 scenarios)
                                      ├── Owner dashboard preview
                                      ├── Compounding-revenue table
                                      ├── White-label section
                                      ├── ICP grid
                                      └── ★ DEMO FORM (2-step)
                                                  │
                                                  ▼
                                       GHL CONTACT CREATED
                                       Tag: nemt-demo-request
                                       Pipeline: NEMT Operators
                                       Stage: New Demo Request
                                                  │
                                                  ▼
                                       CALENDLY / GHL CALENDAR
                                       30-min strategy call booked
                                                  │
                                       ┌──────────┴──────────┐
                                       ▼                     ▼
                                  SHOWED                   NO-SHOW
                                       │                     │
                                       ▼                     ▼
                                 DEMO + ROI            3-EMAIL SEQUENCE
                                  REPORT                  + 1 SMS
                                       │                     │
                                       ▼                     ▼
                                 ┌─ CLOSED-WON          REBOOK or
                                 │                      DEAD-LEAD TAG
                                 │
                                 ▼
                          ONBOARDING (72hr SLA)
                                 │
                                 ▼
                          LIVE OPERATOR
                                 │
                                 ▼
                          QBR + UPSELL
```

## Stage-by-stage

### Stage 1 — Cold Awareness
- **Cold email** (Instantly.ai): 250/wk, 4-step sequence, opens to demo CTA.
- **LinkedIn**: 50 manual touches/wk by SDR on Persona 1 & 2.
- **Conference**: NEMTAC, state Medicaid summits, MCO events.

### Stage 2 — Landing Page
- Single-page (current Lovable build is the foundation).
- Goal: get to demo form. Everything funnels to it.
- Two-step form (qualifier + slot picker) to maximize start rate.

### Stage 3 — Demo Booked → Pre-Demo
- **Confirmation email** with: case study, video walkthrough, "send me your missed call count for last week".
- **24hr SMS reminder**.
- **2hr SMS reminder** with Zoom link.

### Stage 4 — The Demo (30 min)
- 5 min: discovery (vehicles, calls/day, staff, current tools, pain).
- 15 min: live Godspeed walkthrough + show their numbers in our ROI calculator.
- 7 min: pricing + guarantee.
- 3 min: ask for the close. See [`sops/client-demo-script.md`](../sops/client-demo-script.md).

### Stage 5 — Close
- If yes: Stripe link sent on the call, signed within 24hr.
- If "need to think": move to 5-touch nurture (case studies + ROI report).
- If no: dead-lead tag, revisit in 90 days.

### Stage 6 — Onboarding (<72hr SLA)
1. Stripe paid → kickoff form auto-sent.
2. Subdomain created via GoDaddy API.
3. Lovable project cloned and white-labeled.
4. GHL sub-account created from snapshot.
5. Retell agent provisioned.
6. ElevenLabs voice tuned.
7. Phone number assigned + forwarding configured.
8. Operator's existing customer list imported.
9. Go-live call with operator + dispatcher training.

### Stage 7 — Live → QBR → Upsell
- Week 1: daily check-ins.
- Week 2–4: weekly Loom updates with KPIs.
- Month 2+: monthly QBR.
- Month 4: upsell trigger (driver app, broker EDI, multi-location).

## Conversion targets (planning model)

| Stage | Conversion | Outputs |
|---|---|---|
| Cold email → reply | 4% | 10 replies / 250 sent |
| Reply → demo booked | 40% | 4 demos / 10 replies |
| Demo booked → showed | 65% | 2.6 demos / 4 booked |
| Demo showed → closed | 35% | ~0.9 close / 2.6 shown |
| **Per 250 cold emails:** | **~0.9 closes** | |

At Founder tier ($1,997 MRR + $2,500 setup), each close = ~$26k LTV at 12-month ACV.
250 emails → ~$23k expected value. Run 1,000 emails/wk → ~$92k expected MRR-equivalent / wk.

## Funnel KPIs to watch weekly

- Landing-page demo form submit rate (target: 4%+)
- Demo-form completion rate (target: 70%+)
- Demo show rate (target: 65%+)
- Demo close rate (target: 35%+)
- Onboarding-to-live SLA hit rate (target: 100% under 72hr)
- 60-day capture guarantee invocations (target: 0)
