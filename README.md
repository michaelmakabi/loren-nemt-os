# Loren AI — NEMT Operating System

> The AI Operating System for Non-Emergency Medical Transportation operators.
> One platform. One brand. One source of truth. Built by Loren AI.

**Live marketing site:** [nemt-os.ai-loren.com](https://nemt-os.ai-loren.com) *(after Lovable custom-domain verification)*
**Lovable preview:** https://preview--ne-me-transpo-hub.lovable.app
**Reference deployment (client):** https://godspeedtrans.ai-loren.com

---

## What this repo is

This is the **HCP (Highest-Capability Product) implementation** of the Loren AI platform for the NEMT vertical. It contains:

- The **brand strategy and positioning** that powers every deliverable in this vertical.
- The **AI agent prompt library** (Grace receptionist, dispatch coordinator, follow-up, reactivation, VSL wizard).
- The **automation playbook** (missed-call text-back, qualification, booking, reactivation).
- The **GoHighLevel build spec** (pipelines, stages, tags, custom fields, workflows).
- **Integration runbooks** for Retell AI, ElevenLabs, Stripe, GoDaddy, and GHL.
- **Deployment SOPs** for white-labeling the system to a new operator in <72 hours.
- **Client-facing artifacts** — pitch deck, ROI worksheet, onboarding checklist.

The actual marketing frontend lives in Lovable. This repo is the **operating brain** behind the entire vertical.

---

## Vertical thesis (the one-liner)

> Every NEMT operator loses 10–20+ calls a day. At an $80 average ride value, that's $800–$1,600/day evaporating. Loren AI is the platform that captures those calls, books the rides, dispatches the drivers, and runs the back office — in one branded system, 24/7, for less than the cost of a single dispatcher.

---

## Repo map

```
loren-nemt-os/
├── README.md                          ← you are here
├── ARCHITECTURE.md                    ← system architecture overview
├── ROADMAP.md                         ← scaling roadmap
├── BRAND.md                           ← non-negotiable brand standards
├── docs/                              ← strategy + audit + presentation
│   ├── brand-strategy.md
│   ├── market-positioning.md
│   ├── unique-mechanism.md
│   ├── offer-stack.md
│   ├── ideal-customer-profile.md
│   ├── funnel-architecture.md
│   ├── ai-automation-map.md
│   ├── scaling-roadmap.md
│   ├── audit-report.md                ← live-site audit + gap list
│   ├── 21st-dev-component-map.md      ← exact component swaps to kill AI slop
│   └── client-presentation-outline.md
├── prompts/                           ← Loren AI agent prompts
│   ├── grace-ai-receptionist.md
│   ├── dispatch-coordinator.md
│   ├── followup-reactivation.md
│   ├── vsl-wizard.md
│   └── conversion-copywriter.md
├── automations/                       ← cross-system flows
│   ├── missed-call-textback.md
│   ├── lead-qualification.md
│   ├── appointment-booking.md
│   ├── reactivation-campaign.md
│   └── facility-account-onboarding.md
├── ghl/                               ← GoHighLevel build spec
│   ├── pipelines-and-stages.md
│   ├── tags-and-segments.md
│   ├── custom-fields.md
│   └── workflows.md
├── integrations/                      ← API runbooks
│   ├── retell.md
│   ├── elevenlabs.md
│   ├── stripe.md
│   └── ghl.md
├── deployment/                        ← infra SOPs
│   ├── subdomain-sop.md
│   └── lovable-sop.md
├── sops/                              ← operating procedures
│   ├── client-onboarding.md
│   ├── client-demo-script.md
│   └── white-label-setup.md
├── frontend/                          ← notes on the Lovable build
└── branding/                          ← logo, color, type references
```

---

## Brand non-negotiables (read before touching anything)

- **Loren AI** is always two words, both capitalized. Not "LorenAI", not "Loren-AI", not "loren ai".
- Every public surface ships with the `Powered by Loren AI` footer credit.
- The Lovable badge must be hidden on every published project.
- Live deployments live on `*.ai-loren.com` (managed via GoDaddy API).
- Copy tone is **operator-voice, direct, tension-led, conversion-first** — never corporate, never hedging.

Full brand standards: see [`BRAND.md`](./BRAND.md).

---

## Quick links for operators on this project

| What you need | Where it lives |
|---|---|
| Why we win this vertical | [`docs/unique-mechanism.md`](./docs/unique-mechanism.md) |
| The offer we're selling | [`docs/offer-stack.md`](./docs/offer-stack.md) |
| Who we're selling to | [`docs/ideal-customer-profile.md`](./docs/ideal-customer-profile.md) |
| Funnel map | [`docs/funnel-architecture.md`](./docs/funnel-architecture.md) |
| Live-site audit | [`docs/audit-report.md`](./docs/audit-report.md) |
| Stop-AI-slop component swaps | [`docs/21st-dev-component-map.md`](./docs/21st-dev-component-map.md) |
| Client demo script | [`sops/client-demo-script.md`](./sops/client-demo-script.md) |
| White-label a new operator | [`sops/white-label-setup.md`](./sops/white-label-setup.md) |

---

© 2026 Loren AI · Built and operated by Master Makabi · Powered by Loren AI
