# ElevenLabs — Voice Runbook

## Default voice — "Grace"
- Profile: warm, calm, dispatcher-grounded, ~35yo, neutral US accent with slight Midwestern roundness
- Settings:
  - Stability: 0.55
  - Similarity boost: 0.78
  - Style: 0.15
  - Speaker boost: ON
- Use case: Founder + Growth tier default

## Tier-specific voices
- **Growth +**: optional Spanish-language Grace (same persona, bilingual)
- **Fleet**: custom voice cloning available — operator can record 3 min of their preferred voice and we generate a per-brand voice (HIPAA-clean recording protocol)

## Voice swap procedure (operator request)
1. Operator selects from voice library OR provides recording.
2. Create voice profile in ElevenLabs.
3. Tune stability/similarity per voice.
4. Update Retell agent config.
5. A/B test with 50 calls before full cutover.

## Output formatting rules
- Always sound natural, never over-cheerful
- Pauses inserted with `…` for hesitation, `<break time="0.4s"/>` for explicit pauses
- Numbers spoken naturally: "eight forty-five" not "eight colon four five"
- Addresses spoken intelligibly: "four-one-nine Maple" not "four hundred nineteen Maple"
