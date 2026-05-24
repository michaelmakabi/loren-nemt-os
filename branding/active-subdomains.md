# Active Subdomains on ai-loren.com (NEMT vertical)

## Marketing / master
- `nemt-os.ai-loren.com` — Loren AI NEMT marketing site (live A record; Lovable verification pending)

## Reference / case-study clients
- `godspeedtrans.ai-loren.com` — Godspeed Transportation, Detroit (live)

## In-flight onboardings
- _(none yet — first 3 operators incoming)_

## How to register a new subdomain
1. Run `godaddy_create_subdomain` with the slug
2. Get Lovable verification token from operator's Lovable project
3. Add TXT record `_lovable.{slug}` → `lovable_verify={token}`
4. Add entry to this file
5. Update `CLAUDE.md` active subdomains list in Makabi Memory
