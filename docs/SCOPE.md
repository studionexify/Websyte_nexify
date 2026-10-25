# Studio Nexify — Website Scope Discussion (Pre-Design)

## Context
- Repo is empty; greenfield static portfolio + parallax site for www.studionexify.com.
- Goal of this phase: agree on must-do vs. time-waste before choosing visual design.

## MUST DO
- Positioning line: "Design + 3D print, concept to part" — design team is the moat, not printers.
- Industry pages (one per vertical, SEO landing pages): Corporate gifting, Architects/Interiors, Bespoke products, Industrial/replacement parts, Automotive, Religious idols/artifacts, Toys/stationery.
- Portfolio: real photos, before/after (broken part → printed replacement), material + process tag per project.
- Materials & processes page (FDM/SLA/SLS/resin, PLA/PETG/ABS/ASA/Nylon/CF/TPU) — engineers buy on specs.
- Quote/RFQ form with STL/STEP upload + WhatsApp CTA (India buys on WhatsApp).
- Corporate gifting: MOQ, lead time, branding options, catalogue PDF.
- Trust: client logos, process steps, turnaround, "Made in Vadodara, ships pan-India + export".
- Performance: static, <2s LCP on 4G, mobile-first, lazy-loaded images.
- Local + intent SEO: Google Business Profile, schema.org LocalBusiness, per-industry meta.
- Analytics + conversion tracking (GA4/Plausible, form + WhatsApp clicks).

## TIME WASTE (skip / defer)
- Heavy parallax everywhere — use 1–2 hero/section effects only; full parallax hurts mobile + SEO.
- Live 3D model viewer on every product — only for 3–5 hero pieces, if at all.
- Instant online price calculator — custom work varies too much; RFQ wins.
- E-commerce/cart — not a store; defer until a catalogue SKU line exists.
- Blog at launch — only if someone commits to 2 posts/month.
- Multi-language — English first; Hindi/Gujarati only for religious vertical later.
- Chatbot — WhatsApp does the job.
- "And many more" industry list — dilutes; show 6–7 strong verticals.

## Challenges to premises
- Religious idols + toys + automotive on one site risks a confused brand → use segmented industry entry paths from home.
- "Static" conflicts with RFQ file upload → needs Netlify/Formspree/Supabase or similar backend.

## Agreed inputs
- Primary verticals (homepage hero, 3 entry paths): Corporate gifting, Industrial/Automotive, Architects/Interiors.
- Secondary verticals (grid below fold): Bespoke products, Religious artifacts, Toys/stationery, Advanced printing.
- Content: real photos + client list ready → no placeholders, portfolio-led design.

## Existing Shopify site (from search index; direct fetch blocked by sandbox network policy)
- Positioning: custom 3D-printed items for home, office, corporate gifts.
- Collections: fidget toys, keychains, coasters, kitchen, bathroom, vases, desk organisers, storage.
- Sample SKUs: Adhesive Wall Hook ₹99, Hatsune Miku Clicker ₹199, Stackable Glasses Tray ₹439, Wiggle Organiser Small ₹629 / Large ₹1,230, Pumpkin Container ₹659, Remote Holder w/ Tray ₹1,600.
- Materials stated: PLA/PETG/ABS/ASA; print-on-demand; replace-on-proof policy; "made in Vadodara studio".
- Instagram: @studio.nexify ("3D printing & CAD modelling, designed & manufactured in Vadodara").
- Gap: site reads as ₹99–₹1,600 consumer D2C store; zero industrial/architect/automotive proof → new site must reposition to B2B studio.

## Migration must-haves
- 301 redirects for every /products/* and /collections/* URL → matching portfolio/gifting pages (protect existing SEO).
- Convert SKU catalogue → "Gifting Catalogue" + portfolio entries (no prices, "Request quote/bulk").
- DECIDED: Stop D2C. B2B-only static showcase; all CTAs = RFQ form / WhatsApp / bulk quote.
- DECIDED: Fresh brand direction (no legacy colours/fonts carried over).

## Next phase (after agreement)
- Design direction: visual style, palette, typography, parallax moments, page map.
- Stack proposal: static site generator (Astro) + form backend for RFQ uploads + Netlify/Vercel hosting.

## Design decisions (round 2)
- Visual direction: Luxury Atelier — warm neutrals, serif display headings, large photography.
  - Mitigation for industrial/auto credibility: spec-sheet module (material, tolerance, process) on industrial pages.
- Parallax: all 4 approved, each used once on the homepage, GPU-only transforms, `prefers-reduced-motion` fallback, simplified on mobile.
  1. Hero layer-build (object prints layer-by-layer on scroll)
  2. Pinned vertical scroll-strip: Gifting → Industrial/Auto → Interiors
  3. Before/after slider (broken part vs printed replacement)
  4. Process timeline depth layers: Sketch → CAD → Print → Finish
- Stack (default, no preference given): Astro static + Netlify (Forms w/ STL/STEP upload, `_redirects` for Shopify 301s).
