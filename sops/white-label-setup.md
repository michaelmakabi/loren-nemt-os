# White-Label Setup Playbook

## Inputs needed from operator (from kickoff form)

- Company name
- Owner name
- Primary city + service area zips
- Logo (SVG preferred, PNG fallback)
- Brand colors (primary + accent hex, OR pick from a swatch)
- Preferred phone-tree greeting wording (override of default)
- Voice preference (Grace default, Spanish add-on, custom voice)
- Current phone number (to forward)
- Dispatcher cell (for escalations)
- Top 5 facility contracts (for facility account setup)
- Broker mix (which brokers are they on?)

## Theming the Lovable project

1. Replace logo across header + footer + favicon set
2. Update Tailwind theme tokens: `primary`, `accent`, `surface`
3. Update OG image with operator's branding
4. Update meta tags: title, description, og:title, og:description, og:url, twitter:*
5. Update every "Loren AI" surface-facing string → operator's name
   - **EXCEPT** the "Powered by Loren AI" footer credit, which stays
6. Update canonical URL + sitemap to subdomain

## Theming the Retell + Grace voice

1. Update `OPERATOR_NAME`, `OPERATOR_CITY`, `OPERATOR_OWNER_NAME`, `DISPATCHER_NAME`, `DISPATCHER_PHONE` in agent variables
2. Update phone-tree opening line if operator wants custom
3. Update service area validation
4. Update broker list per operator's contract mix

## Theming the GHL sub-account

1. Update logo + business profile
2. Update sender email + SMS sender name
3. Update business hours per operator
4. Inject custom field defaults

## Theming the customer-facing portal

1. Branded booking page on subdomain
2. Branded confirmation emails
3. Branded SMS sender name (where supported)
4. Branded driver app PWA shell (Growth tier+)

## Customer experience test (run before go-live)

Pretend to be a patient. Book a ride end-to-end:
- [ ] Site looks like operator's brand (not Loren AI's)
- [ ] Greeting uses operator's name
- [ ] Confirmation email + SMS use operator's branding
- [ ] Dashboard accessible to operator
- [ ] No visible Loren AI references anywhere customer-facing (except hidden footer credit linking to ai-loren.com)
