# Retell AI — Integration Runbook

## What Retell does for us
- Hosts the live voice agent runtime (LLM + STT + TTS pipeline)
- Provides telephony (numbers + SIP / forwarding)
- Real-time tool-calling so Grace can hit GHL / GoDaddy / Stripe mid-call

## Per-client setup (~20 min)

1. Create new agent in Retell dashboard.
2. Paste Grace system prompt (see `prompts/grace-ai-receptionist.md`) with operator variables substituted.
3. Set voice = ElevenLabs Grace (see `integrations/elevenlabs.md`).
4. Configure model = GPT-4o-mini (latency) with Claude Haiku fallback.
5. Configure tools:
   - `lookup_ride_by_phone(phone)` → GHL contact lookup
   - `create_ride(payload)` → GHL opportunity creation
   - `cancel_ride(ride_id)` → GHL status update
   - `notify_dispatcher(message)` → SMS to dispatcher cell
   - `escalate_to_human()` → warm transfer to dispatcher
6. Provision phone number in Retell.
7. Forward operator's existing number → Retell number (if keeping number, port via Retell support).
8. Test with 5 scripted call scenarios (see `sops/client-onboarding.md` test pack).

## Operator-specific variables
| Var | Source |
|---|---|
| OPERATOR_NAME | from kickoff form |
| OPERATOR_CITY | from kickoff form |
| OPERATOR_OWNER_NAME | from kickoff form |
| DISPATCHER_PHONE | from kickoff form |
| SERVICE_AREA_ZIPS | from kickoff form |
| RATE_SHEET_SUMMARY | from kickoff form |

## Webhooks Retell pushes back to GHL
- `call.started` → create contact note
- `call.ended` → finalize note + push transcript
- `call.tool_invoked` → log tool usage
- `call.escalated` → notify dispatcher

## Eval cadence
- Weekly: sample 20 random calls, score 5 dimensions (greeting, intent capture, completeness, policy compliance, tone)
- Monthly: NEMT-specific eval pack (15 scripted scenarios run via Retell simulator)
