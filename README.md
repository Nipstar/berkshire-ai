# AI Services Berkshire

Marketing website for **AI Services Berkshire** — the Berkshire-focused satellite of [Antek Automation](https://www.antekautomation.com). Serves the M4 corridor and Thames Valley (Reading, Slough, Newbury, Maidenhead, Bracknell, Wokingham, Windsor) with AI voice agents, chatbots, and workflow automation.

**Live:** https://aiservicesberkshire.co.uk
**Parent:** Antek Automation (Andover, Hampshire) — Certified Retell AI Partner — ICO ZC133436 — DUNS 235593033

## Stack

Static single-page `index.html` with inline CSS/JS. Vanilla JS only. Google Fonts (Sora + DM Sans). No build step.

## Develop

```bash
open index.html
# or any static server:
python3 -m http.server 8000
```

## Deploy

Static host (Cloudflare Pages / Vercel / Netlify / GitHub Pages). Required files: `index.html`, `privacy-policy.html`, `terms.html`, `robots.txt`, `sitemap.xml`, `images/`.

## Tracking

GA4 stream `G-2QB7BQBEF3` + Microsoft Clarity `ww6ws9q0if` + Retell chat widget `agent_1c30d12544e2aedfc07ac8be1c`. See [CLAUDE.md](CLAUDE.md) for the full integration map.

## License

All rights reserved — Antek Automation © 2026
