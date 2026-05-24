# Live-Site Audit Report

**Target:** https://preview--ne-me-transpo-hub.lovable.app
**Date:** 2026-05-24
**Auditor:** Loren AI Ops (Claude)
**Severity legend:** 🔴 Critical · 🟡 Important · 🟢 Polish

---

## TL;DR

The site is **80% of the way to enterprise-grade**. Strategy, structure, and copy are mostly right. What's holding it back is (1) brand spelling inconsistency, (2) a few visually generic sections that scream "AI generated", and (3) missing technical SEO + conversion plumbing. None of this is deep — all fixable in a single sprint.

**Top-3 fixes if you only have an hour:**
1. Global find/replace: `LorenAI` → `Loren AI` (currently broken in nav + footer brand mark).
2. Replace the platform-features grid and ICP grid with 21st.dev curated component swaps (see [21st-dev-component-map.md](./21st-dev-component-map.md)) — these are the two sections that read as "AI slop" today.
3. Add real OG image + favicon + sitemap + robots and verify the demo form actually creates a GHL contact end-to-end.

---

## 🔴 Critical (must fix before paid traffic)

### C1. Brand name spelled `LorenAI` (one word) in nav + footer brand mark
**Where:** top-left nav, bottom-left footer brand mark.
**Master Makabi's standard:** "Loren AI" is always two words, both capitalized.
**Fix:** find/replace `LorenAI` → `Loren AI` across the codebase.

### C2. Lovable badge presence not verified
**Why critical:** brand SOP says "Hide Lovable badge" toggle ON for every project, no exceptions.
**Fix:** confirm toggle is ON in Lovable project settings.

### C3. Custom domain not yet wired
**Status:** DNS A record live at `nemt-os.ai-loren.com` (just provisioned). Lovable verification token pending.
**Fix:**
1. In Lovable → Project Settings → Custom domain → enter `nemt-os.ai-loren.com`.
2. Copy the verification token Lovable provides.
3. Drop it back to me — I'll write the `_lovable.nemt-os` TXT record via GoDaddy API.
4. Verify in Lovable. SSL auto-provisions.

### C4. Demo form submission flow not verified
**Risk:** if the form doesn't push to GHL, every demo request is lost.
**Fix:** smoke test — submit the form with a test record → confirm a contact appears in the GHL NEMT Operators sub-account with tag `nemt-demo-request`.

### C5. Footer attribution malformed
**Current:** "© 2026 Loren AI. All rights reserved. · Powered by Loren AI"
**Issue:** the "Powered by Loren AI" credit links to `https://ai-loren.com` which is correct, but the entire footer copyright also says "Loren AI" — redundancy reads cheap.
**Fix:** rewrite footer:
> © 2026 Loren AI · All rights reserved · Built and operated from Florida · [Powered by Loren AI →](https://ai-loren.com)

---

## 🟡 Important (fix this sprint)

### I1. Hero CTA stack is too cluttered
**Current:** three CTAs — "Book a Demo" / "See Godspeed Case Study" / "Calculate Your Savings".
**Issue:** competing CTAs split intent. Demo is the conversion. The other two are scroll anchors disguised as CTAs.
**Fix:** primary CTA = "Book a Demo" (filled, brand color). Secondary as plain underlined links: "See live Godspeed deployment →" and "Run my ROI →".

### I2. Hidden-leak section uses generic icon tiles (reads as AI slop)
**Current:** 8 tiles with `####` headings and short paragraphs. Visually flat.
**Fix:** swap to the **21st.dev "Bento Grid" or "Feature Steps" component** — see [21st-dev-component-map.md](./21st-dev-component-map.md) item §2. Adds visual hierarchy, kills the "AI list" feel.

### I3. ROI calculator outputs need accent + animation
**Current:** static number readouts.
**Fix:** animate the result numbers (count-up on input change), add a "Get this report by email" CTA next to the results, push the email + their numbers to GHL with a `roi-calculator-engaged` tag.

### I4. Platform-features grid is the single most "AI generated" looking section
**Current:** 7 generic feature cards with icon + heading + 1-sentence description.
**Fix:** replace with **21st.dev "Feature Sections" or "Tabs Showcase"** — see [21st-dev-component-map.md](./21st-dev-component-map.md) item §3. Show a real screenshot per feature, not an icon.

### I5. Call-demo audio section
**Current:** 8 scenario cards labeled "Play Sample Call" — no evidence the audio actually plays in the preview build.
**Fix:** wire real audio files (record once with ElevenLabs + a NEMT-trained Grace prompt) and ensure the play button works. If audio isn't ready, mark "Audio coming soon — book a demo to hear live" instead of a dead button.

### I6. Owner-dashboard preview is text-only KPI tiles
**Current:** 9 KPI cards rendered as text.
**Fix:** wrap in a real "dashboard chrome" container (dark surface, faux nav, faux date picker) so it reads as a screenshot, not a list. Use the **21st.dev "Dashboard Preview" component**.

### I7. White-label section is text-only ("Custom Logo / Custom Colors / Custom Website…")
**Current:** plain tile grid.
**Fix:** show a real before/after — generic Lovable look vs. Godspeed branded look. Two side-by-side phones.

### I8. ICP "Who This Is For" grid is the second most AI-generated-looking section
**Current:** 9 plain bullet tiles.
**Fix:** swap to **21st.dev "Logo Cloud" or "Stat-with-icon row"** so it reads as confident, not generic.

### I9. Missing technical SEO
**Missing:** sitemap.xml, robots.txt, JSON-LD structured data (Organization + SoftwareApplication schema), canonical URL.
**Fix:** add per the standard subdomain deployment checklist in `CLAUDE.md`.

### I10. No social proof above the fold
**Current:** Godspeed appears only at the case study section.
**Fix:** add a single-line "trusted by Detroit's Godspeed Transportation (25 drivers · 420 trip legs / day · Wayne County Medicaid D-1)" sub-hero. One-line proof beats a logo cloud at this stage.

---

## 🟢 Polish (next iteration)

### P1. Mobile typography scales too aggressively
The hero H1 at 375px wraps awkwardly. Tighten line-height and max-width.

### P2. The "Operations Dashboard Today" widget in the hero
Looks like a static screenshot. Either animate one number (e.g., calls-answered ticks up) or label it "Sample dashboard view" to set expectation.

### P3. Footer nav anchors mostly go to `#` (placeholder)
"Privacy" and "Terms" are placeholder links. Either ship real pages or remove until ready.

### P4. Compound-revenue table needs a slider
Currently 3 static rows (3 / 5 / 10 rides per day). Add a slider so the operator can drag and see their number.

### P5. The 8 audio scenarios are too many
Cut to the 4 strongest (New Ride Request, Facility Call, After Hours, Wheelchair Accommodation). Pad scenarios don't add value — they dilute.

### P6. Add an exit-intent modal
Trigger on mouse leave: "Before you go — get the 1-page ROI report for your fleet size. Drop your email." → GHL.

### P7. Add a sticky bottom-of-page CTA on mobile
"Book a Demo" pinned to mobile viewport bottom after first scroll.

---

## What's already GOOD (don't change)

✅ The hero pain frame ("Stop Losing Medical Transportation Calls, Rides, and Revenue.") is on-brand and operator-voice.
✅ The hidden-leak narrative is correct — leads with pain, not feature.
✅ The ROI calculator concept is exactly right.
✅ Human-vs-AI comparison table is well-structured.
✅ Godspeed live deployment as social proof is the single best asset on the page.
✅ The compounding-revenue math is the most persuasive section on the page.
✅ Footer carries "Powered by Loren AI" — brand SOP satisfied (after I-C5 fix).

---

## Engineering checklist (for whoever opens the Lovable build)

```
[ ] Global find/replace LorenAI → Loren AI
[ ] Hide Lovable badge toggle ON
[ ] Add custom domain nemt-os.ai-loren.com (get TXT token, share back)
[ ] Update OG image to NEMT-specific creative
[ ] Add favicon set (SVG / 16 / 32 / 180 / 512 / ICO)
[ ] Add manifest.json
[ ] Add sitemap.xml + robots.txt
[ ] Add JSON-LD Organization + SoftwareApplication schema
[ ] Wire demo form → GHL webhook (verify contact created with tag)
[ ] Wire ROI calculator email → GHL tag
[ ] Replace platform-features grid (21st.dev swap §3)
[ ] Replace ICP grid (21st.dev swap §4)
[ ] Wrap dashboard preview in chrome (21st.dev swap §5)
[ ] Animate ROI result numbers
[ ] Real audio for at least 4 demo calls (cut from 8 → 4)
[ ] Sticky mobile CTA
[ ] Exit-intent modal
[ ] Smoke test on iPhone SE + iPhone 15 Pro Max + Samsung Galaxy
```

---

## Final score

| Dimension | Score | Notes |
|---|---|---|
| Strategy / narrative | 9/10 | Pain → mechanism → proof → math → close. Sequencing is right. |
| Copy quality | 7/10 | Mostly operator-voice. A few sections drift into "feature-list voice". |
| Visual hierarchy | 6/10 | Two grids read as AI-generated. Fix with 21st.dev swaps. |
| Brand compliance | 5/10 | `LorenAI` typo blocks shipping. Easy fix. |
| Technical SEO | 4/10 | Missing OG, favicon, sitemap, schema. |
| Conversion plumbing | 5/10 | Form → GHL flow not verified. ROI calculator not capturing leads. |
| Mobile UX | 7/10 | Mostly fine. Hero needs tightening at 375px. |
| **Overall (current)** | **6.4/10** | |
| **Overall (after this sprint)** | **9.0/10 projected** | |
