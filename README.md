# firsthourleads-site

Public landing page for **First Hour Leads** — Tony McMurtrey's done-for-you AI follow-up service for local service businesses in Texas.

**Live:** https://firsthourleads.com (via custom domain when DNS is configured)

## Stack
Static HTML + CSS. No JS, no build step. Served by GitHub Pages.

## Custom domain
`CNAME` file declares `firsthourleads.com`. To make the domain live:

1. Register `firsthourleads.com` (e.g. Cloudflare Registrar — ~$10/yr).
2. Point DNS at GitHub Pages:
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   AAAA  @     2606:50c0:8000::153
   AAAA  @     2606:50c0:8001::153
   AAAA  @     2606:50c0:8002::153
   AAAA  @     2606:50c0:8003::153
   CNAME www   HAS-deploy.github.io
   ```
3. In repo Settings → Pages → Custom domain, enter `firsthourleads.com` + check "Enforce HTTPS".

Until the domain is registered, the site is reachable at:
`https://has-deploy.github.io/firsthourleads-site/`

## Edit + ship
```bash
# clone
git clone https://github.com/HAS-deploy/firsthourleads-site
cd firsthourleads-site

# edit index.html / styles.css

# commit + push
git add . && git commit -m "tweak copy" && git push
# Pages auto-deploys in ~30 seconds
```

## Backend
The actual sales-automation stack lives on a private server (spldbserver, Tailscale / SSH tunnel only access). This repo is **public** and **frontend only** — no API keys, no system internals, no client data, no OpenClaw references.
