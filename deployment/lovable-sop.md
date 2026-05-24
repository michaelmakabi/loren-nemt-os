# Lovable Project SOP

## Settings checklist for EVERY Loren AI project

- [ ] **Hide Lovable badge** → ON (mandatory, no exceptions)
- [ ] **Public remixing** → OFF (for client-facing builds)
- [ ] **Project name** matches the subdomain slug
- [ ] **Custom domain** added and verified
- [ ] **Build settings** → SSR off (we ship static for max speed)
- [ ] **Analytics** → connected to Loren AI's PostHog or Plausible

## File / component standards (inside the Lovable project)

- Single-page (or near-single-page) React + Tailwind, shadcn/ui base
- Lucide icons only (no AI-art icons)
- Color palette per brand: deep navy primary, oxygen blue accent, alert amber for KPIs, clean whites
- Font: Inter (or Geist) — sans-serif only, no decorative fonts
- Motion: subtle entrance fades, scroll-triggered count-ups for stats
- Section structure: hero → leak → ROI → comparison → platform → case study → demos → dashboard → compound → white-label → ICP → demo form → footer

## 21st.dev integration

Two paths:
1. **CLI (if shadcn-installed):** `npx shadcn@latest add @{21st-component-url}` then import.
2. **Manual copy:** open the component on 21st.dev → copy JSX → paste into Lovable's component file → adjust imports for shadcn/ui pieces.

See `docs/21st-dev-component-map.md` for the section-by-section swap plan.

## Per-publish gate

Before every publish, verify:
- [ ] No instances of `LorenAI` (must be `Loren AI`)
- [ ] Footer carries "Powered by Loren AI" link to https://ai-loren.com
- [ ] Lovable badge is hidden
- [ ] OG / favicon present
- [ ] All `#` placeholder links replaced or removed
- [ ] Mobile renders correctly at 375px
- [ ] Demo form actually creates a GHL contact (smoke test)
