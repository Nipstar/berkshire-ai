# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Marketing website for **AI Services Berkshire** — the Berkshire-focused satellite of Antek Automation. Targets Thames Valley + M4 corridor businesses (Reading, Slough, Newbury, Maidenhead, Bracknell, Wokingham, Windsor) seeking AI voice agents, chatbots, and workflow automation.

**Live site:** https://aiservicesberkshire.co.uk
**Parent company:** Antek Automation, Andover, Hampshire (Certified Retell AI Partner). ICO `ZC133436`. DUNS `235593033`.
**Position in network:** Tier 2 county hub (sibling of `hampshire-ai`). Per network playbook v3 Section E.

## Tech Stack

Single `index.html` with all CSS and JS inline. No build step, no frameworks, no dependencies. Vanilla JS only. Google Fonts (Sora display, DM Sans body). Open `index.html` in browser to develop.

## File Structure

- `index.html` — main landing page (all CSS/JS inline)
- `privacy-policy.html` — legal privacy policy
- `terms.html` — legal terms of business
- `robots.txt` / `sitemap.xml` — SEO files (canonical: `aiservicesberkshire.co.uk`)
- `images/` — assets

## Tracking + integrations (Phase 1 installed)

- **GA4:** measurement ID `G-2QB7BQBEF3` (data stream under property `Antek Main` 511254114, shared across the Antek network). Custom dimensions: `page_town=berkshire`, `page_type=home`.
- **Microsoft Clarity:** project `ww6ws9q0if` (single shared project; segment by `site_domain` + `page_town` custom tags).
- **n8n webhook:** contact form POSTs enriched payload (name, email, phone, business, message, source, page_url, page_town, utm_*, referrer, session_pages, time_on_page_s, ga_client_id, ga_session_id) to `https://antekauto.app.n8n.cloud/webhook/29e3a09b-5b23-489b-a800-a07262afb4cb`. Honeypot field name = `website`.
- **Retell chat widget:** agent `agent_1c30d12544e2aedfc07ac8be1c`, public key `public_key_b96440ad931cbd5326e4d`. Per-site context via `data-dynamic='{"site":"berkshire","domain":"aiservicesberkshire.co.uk"}'`. Add `aiservicesberkshire.co.uk` + `www.aiservicesberkshire.co.uk` to Retell agent allowed-origins.
- **GA4 events fired:** `form_submit`, `phone_click`, `email_click`, `whatsapp_click`, `cal_booking`, `scroll_depth` (25/50/75/90), all tagged with `page_town: 'berkshire'`.
- **Cal.com:** inline booking embed (`antek-automation/30min`).
- **Schema:** Antek parent Organization JSON-LD with DUNS + ICO PropertyValue identifiers. LocalBusiness for AI Services Berkshire with full `areaServed` list. FAQPage with 8 Berkshire-toned Q+A pairs.

## Berkshire positioning (per playbook v3 Section E + brief)

**Target keywords:** ai automation berkshire, ai agency berkshire, ai services berkshire, ai voice agents berkshire, ai chatbots berkshire, m4 corridor ai, thames valley ai, business automation berkshire, ai for reading businesses, ai for newbury businesses

**Areas served:** Reading, Slough, Newbury, Maidenhead, Bracknell, Wokingham, Windsor, Thatcham, Hungerford, plus broader Thames Valley + M4 corridor

**Industry angles:**
- Tech + telecoms (M4 corridor: Microsoft Reading, Oracle Reading, Vodafone Newbury HQ supply chain)
- Financial + professional services (Bracknell, Maidenhead)
- Equestrian + racing (Newbury Racecourse, Lambourn training yards)
- Defence + pharma (AWE Aldermaston supply chain, Roche)
- Retail + hospitality (The Oracle Reading, Windsor tourism)
- Tradespeople + logistics across the Thames Valley

**Validated demand:** 301 GSC impressions network-wide for "ai automation berkshire" at positions 48–72 (per v3 baseline pre-build). New site consolidates this demand under one Berkshire-focused domain.

**Internal-link target:** `/locations/newbury` on antek-2026 → this site (when antek-2026 location page ships per `location-pages-brief.md`).

## Brand + design

- Dark theme: `#0a0f1c` primary bg, `#111827` secondary, `#1a1f2e` cards
- Accents: `#3b82f6` electric blue, `#06b6d4` cyan, `#10b981` emerald (CTA only)
- Typography: Sora display, DM Sans body
- **No warm tones** (zero orange/amber/gold/coral)
- Animation: staggered fade-up on scroll (IntersectionObserver), card hover `translateY(-4px)`, animated gradient orb in hero

## Content rules

- **UK English** throughout (optimise, specialise, colour)
- All FAQ answers + section subtitles already rewritten for Berkshire uniqueness — when editing, preserve distinct wording vs other satellites (per SATELLITE_BUILD_INSTRUCTIONS duplicate-content rules)
- Single H1 (hero), H2 per section, H3 for sub-items
- `lang="en-GB"` on `<html>`
- Mention Reading, Newbury, Slough, Maidenhead, Bracknell, Wokingham, Windsor naturally throughout
- M4 corridor + Thames Valley are the primary positioning hooks

## Quality targets

- Lighthouse 90+ on Performance / SEO / Accessibility / Best Practices
- No console errors
- JSON-LD validates at https://validator.schema.org/
- Dark theme consistent throughout — no white sections
