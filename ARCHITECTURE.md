# ARCHITECTURE.md

## High-level

```
                       ┌──────────────────────────────────────┐
                       │   nemt-os.ai-loren.com  (marketing)  │
                       │   Lovable · static · public          │
                       └──────────────┬───────────────────────┘
                                      │ Book Demo CTA
                                      ▼
        ┌─────────────────────────────────────────────────────┐
        │                    GoHighLevel                       │
        │   ┌───────────┐  ┌──────────┐  ┌──────────────────┐ │
        │   │  CRM      │  │ Pipeline │  │  Workflows       │ │
        │   │  Contacts │  │ Stages   │  │  Tags / Triggers │ │
        │   └───────────┘  └──────────┘  └──────────────────┘ │
        └──────┬─────────────┬───────────────┬─────────────────┘
               │             │               │
               ▼             ▼               ▼
        ┌───────────┐  ┌───────────┐  ┌────────────────┐
        │ Retell AI │  │ElevenLabs │  │  Stripe        │
        │ (voice)   │  │(voices)   │  │  (billing)     │
        └─────┬─────┘  └─────┬─────┘  └─────┬──────────┘
              │              │              │
              ▼              ▼              ▼
       ┌──────────────────────────────────────────────┐
       │  Per-client white-label subdomain            │
       │  {client}.ai-loren.com                       │
       │   ├── branded booking site                   │
       │   ├── customer portal                        │
       │   ├── driver app shell                       │
       │   └── admin/dispatch dashboard               │
       └──────────────────────────────────────────────┘
```

## Layer-by-layer

### 1. Marketing layer — `nemt-os.ai-loren.com`
- **Built in:** Lovable (React/Tailwind, single page).
- **Purpose:** capture qualified NEMT operators, route to demo booking.
- **Components:** hero, hidden-leak, ROI calculator, human-vs-AI comparison, platform overview, Godspeed case study, call demo audio, owner dashboard preview, compounding effect, white-label section, ICP grid, demo form.
- **Conversion target:** book a 30-minute strategy call.

### 2. CRM / orchestration — GoHighLevel
- **Sub-account per client** (white-label tier).
- **Master account** for Loren AI's own pipeline (NEMT operator prospects).
- See [`ghl/`](./ghl/) for the full build spec.

### 3. Voice AI — Retell + ElevenLabs
- Retell handles the call agent runtime (LLM + telephony glue).
- ElevenLabs supplies the voice ("Grace" — see `prompts/grace-ai-receptionist.md`).
- Each client gets a dedicated Retell agent + phone number + tuned voice.

### 4. Billing — Stripe
- Plans: Founder ($1,997/mo) · Growth ($3,497/mo) · Fleet ($6,997/mo). See [`docs/offer-stack.md`](./docs/offer-stack.md).
- Setup fee billed once at deployment; MRR begins after go-live.

### 5. Client surface — `{client}.ai-loren.com`
- Same Lovable codebase, white-labeled per operator.
- Branded with the operator's logo, color, voice, and phone tree.
- Reference build: [godspeedtrans.ai-loren.com](https://godspeedtrans.ai-loren.com).

### 6. DNS / infra
- GoDaddy API for all subdomain DNS.
- Lovable edge IP: `185.158.133.1`.
- TLS auto-provisioned by Lovable.

## Why this architecture wins

1. **One codebase, infinite clients.** White-label by config, not by fork.
2. **No glue code.** GHL handles 80% of orchestration via native workflows.
3. **Voice is hot-swappable.** Same Retell scaffolding, different ElevenLabs voice per client.
4. **Operator never sees the seams.** Their staff and customers experience one branded system.
