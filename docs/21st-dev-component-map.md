# 21st.dev Component Swap Map

> **Goal:** kill the "AI-generated" feel of the live site by replacing generic Lovable-default sections with curated 21st.dev components. The component library at [21st.dev](https://21st.dev) is the antidote to grid-of-cards-with-icon syndrome.

## How to use this doc

Each entry below names:
- The section in the current live build
- Why it currently reads as "AI slop"
- The exact 21st.dev component family to substitute
- The specific replacement layout
- Copy adjustments to ship with the swap

In Lovable, you can either: (a) install components via 21st.dev's CLI (`npx shadcn@latest add ...`) if the project supports shadcn, or (b) copy the JSX directly from 21st.dev's preview pane and paste it into the Lovable component.

---

## §1. HERO — keep, but tighten

**Current state:** ✅ Already strong. Pain headline + sub + CTA stack + dashboard widget.

**Minor 21st.dev swap:** the dashboard widget on the right should use the **"Dashboard Preview" mockup family** (search "dashboard mockup" on 21st.dev). Pick one with a dark surface, faux sidebar, faux date picker, and animated KPI tiles. This makes the right-side mockup look like a real product screenshot instead of a vertical list of stats.

**Copy adjustment:**
- Drop "See Godspeed Case Study" from primary CTA — relegate to a plain underlined link below the buttons.
- Primary CTA: **"Book a Demo"** (filled, brand color).
- Secondary: **"See it live →"** linking to the Godspeed deployment.

---

## §2. "THE HIDDEN LEAK" — swap to Bento Grid

**Current state:** 8 plain tiles with `####` headers and 1-sentence body. Reads as a bulleted list with extra padding.

**21st.dev component family:** **"Bento Grid"** (search "bento" on 21st.dev — many beautiful options).

**Replacement layout:** 2 oversized tiles (left) + 6 small tiles (right grid), or the classic 3-2-2 bento layout. Each tile gets:
- A short bold headline (4–6 words)
- A real number (e.g., "$24k/mo leak", "10–20 calls/day", "60% dispatcher time")
- An icon (use Lucide icons, NOT generic AI sparkle iconography)

**Why this works:** bento layouts have inherent visual hierarchy — the eye doesn't read it as a uniform grid. It reads as a curated story.

**Recommended bento tiles (rewrite):**

| Tile | Size | Headline | Number / Sub | Icon |
|---|---|---|---|---|
| 1 | XL | Missed calls become missed rides | **10–20 calls/day** evaporate at most operators | PhoneOff |
| 2 | M | Dispatcher hours bleed | **60%** of dispatch time = routine confirmations | Clock |
| 3 | M | "Where's my ride?" floods the office | **3.5 inbound calls per booked ride** average | MessageCircle |
| 4 | L | Software stack chaos | **6–8 disconnected tools**, none talk to each other | LayoutGrid |
| 5 | M | No-shows climb without follow-up | **+18% no-show rate** without proactive reminders | UserX |
| 6 | M | Payroll grows, margin doesn't | **$3.5k–$5k/mo** per added dispatcher | Banknote |
| 7 | XL | No visibility into the leak | Owners **can't measure** what they can't see | EyeOff |

---

## §3. "THE PLATFORM" 7-FEATURE GRID — swap to Tabs Showcase

**Current state:** 7 identical-looking cards (AI Call Agent / Auto Dispatch / Driver App / Customer Booking / Admin Dashboard / KPI Dashboard / White-Label). The most "AI generated" section on the page.

**21st.dev component family:** **"Feature Sections — Tabs / Interactive Tabs"** (search "tabs feature" or "feature tabs" on 21st.dev).

**Replacement layout:** vertical tab stack (left) + product screenshot (right). Click a tab → screenshot animates in. This is the layout Linear / Vercel / Stripe all use because it lets the prospect see real product surfaces.

**Tab structure:**

| Tab label | Screenshot to show | Sub-headline |
|---|---|---|
| AI Call Agent | Live Retell-style transcript with caller + AI bubbles | Answers every call in <1 second. Books, qualifies, or escalates. |
| Auto Dispatch | Dispatch board with vehicles + trips on a Gantt | Assigns trips to the right driver. Reshuffles when conditions change. |
| Driver App | Phone-frame screenshot of a driver's trip list | Drivers see their day, update status, navigate — one app. |
| Customer Booking | Branded booking page screenshot | Patients and facilities request rides through your portal. |
| Admin Dashboard | Owner KPI screen | Calls, rides, revenue, drivers, vehicles — one screen. |
| KPI Dashboard | Time-series chart (calls, rides, $) | Date-ranged, exportable. Walk into a board meeting with real numbers. |
| White-Label | Side-by-side: generic vs branded | Your logo, colors, voice, domain — they never see Loren AI. |

**Why this works:** tabbed showcases let the prospect self-select the feature they care about. The product screenshots become the proof. Tile grids ask the prospect to imagine; tab showcases show.

---

## §4. "WHO THIS IS FOR" ICP GRID — swap to Logo Cloud + Stat Row

**Current state:** 9 plain text tiles ("NEMT operators / Ambulette companies / Wheelchair transportation…"). Reads as a checklist, not a positioning statement.

**21st.dev component family:** **"Logo Cloud + Stat Row"** OR **"Pricing-comparison-grid" remixed**.

**Replacement layout:** a single horizontal row of 4 large stat cards with icons, each anchoring a real operator type:

| Card | Icon | Stat | Caption |
|---|---|---|---|
| 1 | Van | **10–75 vehicles** | NEMT, ambulette, wheelchair |
| 2 | Building2 | **Multi-facility contracts** | Dialysis, behavioral health, senior living |
| 3 | Phone | **>10 missed calls/day** | After-hours, weekends, lunch hour |
| 4 | Layers | **3+ disconnected tools** | CRM, scheduler, dispatch, phone, text |

This converts a checklist into a positioning bar.

---

## §5. OWNER DASHBOARD PREVIEW — wrap in dashboard chrome

**Current state:** 9 KPI tiles floating on a page background. Reads as text.

**21st.dev component family:** **"Dashboard Mockup"** family (search "dashboard").

**Replacement layout:** the same 9 KPI tiles, but wrapped in a faux app chrome:
- Dark header bar with "Godspeed Transportation · Operations" + faux date picker + faux user avatar
- Left sidebar nav (faux: Overview / Calls / Rides / Drivers / Reports / Settings)
- KPI tiles in the main canvas (the existing 9 — keep the copy)
- Bottom strip with a small time-series chart

**Why this works:** the same KPIs framed in chrome read as a screenshot of a real product. Without the chrome, they read as a list.

---

## §6. COMPOUNDING REVENUE TABLE — swap to interactive slider

**Current state:** 3 static rows (3 / 5 / 10 rides per day).

**21st.dev component family:** **"Pricing slider"** or **"ROI Calculator"** components (search "slider", "calculator").

**Replacement layout:** a single big slider (1 → 25 extra rides per day) with the result animating in real-time, like the iconic pricing sliders on Stripe / Vercel. Display:
- Daily extra revenue
- Monthly recovered revenue
- Annual recovered revenue

**Email-gate the export:** the result number stays public, but an "Email me this report" button captures the lead → GHL tag `compound-calc-engaged`.

---

## §7. WHITE-LABEL SECTION — swap to Before/After Compare

**Current state:** 8 plain text tiles (Custom Logo / Custom Colors / Custom Website…).

**21st.dev component family:** **"Image Compare"** or **"Side-by-side comparison"** (search "compare").

**Replacement layout:** two phone frames side by side:
- **Left:** generic Loren-AI-look booking page (greyscale).
- **Right:** Godspeed-branded booking page (full color, real logo).
- Slider drag handle in the middle to wipe between them.

**Caption underneath:** "Same engine. Your brand. Your domain. Your phone number. Your voice. The customer never sees Loren AI."

---

## §8. ADD: SOCIAL PROOF BAR ABOVE THE FOLD

**Where:** between hero CTAs and dashboard widget.

**Component:** **"Marquee" or "Logo Cloud"** from 21st.dev.

**For now (we only have one case study):** use a single-line trust bar:

> 🟢 **Live now:** Godspeed Transportation · Detroit · 25 drivers · 420 trip legs / day · Wayne County Medicaid D-1

This is more credible than a fake logo cloud and primes the case-study section.

---

## §9. ADD: TESTIMONIAL CARD AFTER CASE STUDY

**Component:** **"Testimonial Card"** family.

**Content:** a single quote attributable to Shihada Nelson (Godspeed owner). Sample wording — verify with Shihada before publishing:

> "Within the first week, Loren AI caught calls we would have missed and rebooked rides we would have lost. We've been able to run the same fleet without adding a single dispatcher seat."
> — Shihada Nelson, Owner · Godspeed Transportation · Detroit

---

## §10. FOOTER — swap to 4-column footer with sitemap + powered-by

**21st.dev component family:** **"Footer"** with multi-column layout.

**Recommended structure:**

| Column 1 | Column 2 | Column 3 | Column 4 |
|---|---|---|---|
| **Loren AI**<br>Wordmark + tagline | **Platform**<br>AI Receptionist / Dispatch / Portal / Dashboard | **Resources**<br>Godspeed Case Study / ROI Calculator / Book Demo | **Company**<br>About / Contact / Privacy / Terms |

Bottom strip: © 2026 Loren AI · Built and operated from Florida · [Powered by Loren AI →](https://ai-loren.com)

---

## Implementation order (do these in this sequence)

1. **§3 Platform Tabs Showcase** — single biggest visual upgrade.
2. **§2 Bento Grid for Hidden Leak** — second biggest.
3. **§5 Dashboard Chrome** — turns the dashboard tease into a product moment.
4. **§7 Before/After Compare** — sells white-label visually.
5. **§4 ICP Stat Row** — kills the last "list" feel.
6. **§6 Slider** — turns the compound math into an interaction.
7. **§8 Social Proof Bar** — quick win.
8. **§9 Testimonial Card** — pending Shihada signoff.
9. **§10 Footer** — polish.

---

## Why 21st.dev specifically (vs. raw shadcn or Tailwind UI)

- **Curated taste filter.** Components are hand-picked, not auto-generated.
- **Real-product references.** Components are built FROM live SaaS sites, so they look "in the wild", not "in a tutorial".
- **shadcn-compatible.** Drops into the Lovable / React / Tailwind stack cleanly.
- **Free + open.** No licensing friction.
- **Modern motion defaults.** Components ship with subtle motion that screams "premium" without being annoying.

The opposite of "AI slop" is **curated taste applied to real-world references**. That's what 21st.dev provides. We're using it as the taste filter on top of Lovable's speed-of-build.
