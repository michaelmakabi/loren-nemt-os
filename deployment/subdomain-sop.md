# Subdomain Deployment SOP

> Reference: Master Makabi's CLAUDE.md "Standard Subdomain Deployment Checklist"

## For every new operator subdomain on `ai-loren.com`

```
[ ] 1. Create branded favicon set (SVG + ICO + PNG 16/32/180/512)
[ ] 2. Create OG social preview (1200×630)
[ ] 3. Update index.html: full meta tags, OG, Twitter Card, JSON-LD, favicon links, manifest
[ ] 4. Create sitemap.xml + robots.txt with sitemap directive
[ ] 5. Lovable → Publish → Add custom domain → get verification token
[ ] 6. GoDaddy API: create A record + _lovable TXT verification record
        - A: {subdomain} → 185.158.133.1 (TTL 600)
        - TXT: _lovable.{subdomain} → lovable_verify={token}
[ ] 7. Lovable: verify domain → confirm SSL active
[ ] 8. Update canonical URL + OG URL to point to subdomain
[ ] 9. Hide Lovable badge (Project Settings → Hide Lovable badge → ON) — MANDATORY
[ ] 10. Push + publish
[ ] 11. Verify live site on subdomain
[ ] 12. Test OG preview via opengraph.xyz
[ ] 13. Log new subdomain in /branding/active-subdomains.md
[ ] 14. Update Makabi Memory active-subdomains list
```

## For `nemt-os.ai-loren.com` (marketing site) specifically

Status check (as of 2026-05-24):
- ✅ A record live: `nemt-os.ai-loren.com → 185.158.133.1`
- ⏳ Lovable custom-domain add: pending operator action
- ⏳ TXT verification record: pending token from Lovable
- ⏳ Badge hidden: pending verification in Lovable
- ⏳ OG / favicon / sitemap / schema: pending

## Programmatic DNS recipe (Python / curl)
Use the `godaddy_create_subdomain` MCP tool, OR raw curl:

```bash
curl -X PUT "https://api.godaddy.com/v1/domains/ai-loren.com/records/A/{subdomain}" \
  -H "Authorization: sso-key {KEY}:{SECRET}" \
  -H "Content-Type: application/json" \
  -d '[{"data":"185.158.133.1","ttl":600}]'

curl -X PUT "https://api.godaddy.com/v1/domains/ai-loren.com/records/TXT/_lovable.{subdomain}" \
  -H "Authorization: sso-key {KEY}:{SECRET}" \
  -H "Content-Type: application/json" \
  -d '[{"data":"lovable_verify={token}","ttl":600}]'
```
