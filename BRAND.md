# BRAND.md — Non-Negotiable Brand Standards

> If you break one of these on a public deliverable, it gets reverted. No exceptions.

## Naming

| Correct | Incorrect |
|---|---|
| **Loren AI** | LorenAI · Loren-AI · loren ai · LOREN AI |
| **BRiX** | Brix · BRIX · Brix Technologies |
| **1PM AI** | 1pmAI · 1pm.ai (as a brand name in copy) · 1PM-AI |
| **MTIP** | Mtip · M-Tip · M Tip |

## Required attribution

Every public-facing surface (landing page, funnel, dashboard, deliverable PDF, deck) carries:

```
Powered by Loren AI
```

…in the global footer, linked to `https://ai-loren.com`.

## Lovable rules

- **Hide Lovable badge** toggle: ON, every project, every publish.
- **Public remixing**: OFF on any client-facing build.
- Custom domain pattern: `{project-slug}.ai-loren.com`.

## DNS / hosting

- Primary subdomain host: `ai-loren.com`
- Lovable edge IP for A record: `185.158.133.1`
- TXT verification key: `_lovable.{subdomain}` → `lovable_verify={token}`
- Managed via GoDaddy API (credentials in private vault).

## Copy tone (NEMT vertical specifically)

- **Operator-voice.** Speak the way a fleet owner speaks — short sentences, real numbers, no fluff.
- **Tension-led headlines.** Lead with the leak ("Stop losing calls / rides / revenue"), not the feature.
- **Specificity over adjectives.** "$70–$150 per missed ride" > "significant revenue impact".
- **No corporate hedge words.** Remove: "solutions", "leverage", "innovative", "cutting-edge", "synergy".
- **Loss-frame before gain-frame.** The hidden leak comes before the dashboard screenshot, always.

## Voice & visual identity (NEMT)

- Mood: **clinical authority + dispatcher urgency**.
- Color anchors: deep navy / oxygen blue / clean white / alert amber for KPIs.
- Type: sharp sans-serif (Inter, Geist, or Söhne stand-ins). No serif body text.
- Photography: real fleet vehicles, dispatch ops, drivers — never stock-photo hospital hallways.

## Forbidden patterns

- ❌ Stock photography of doctors in white coats — NEMT is logistics, not clinical.
- ❌ Generic "AI sparkle" iconography — we are a platform, not a chatbot toy.
- ❌ "Revolutionary", "game-changing", "next-generation" — operators don't buy adjectives, they buy ROI.
- ❌ Hero copy that talks about Loren AI before it talks about the operator's pain.

## Approval gate

Anything that ships to a client gets a final brand-pass by Master Makabi. No exceptions.
