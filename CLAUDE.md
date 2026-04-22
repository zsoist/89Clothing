# 8998 — Básicos bien hechos

## What This Is
Premium Colombian t-shirt brand landing page. Pre-launch e-commerce with email capture, countdown timer, and conversion-focused UX. Single-page, zero-dependency vanilla HTML/CSS/JS.

## Stack
- **No framework**: Pure HTML/CSS/JS — single `index.html` (2,170 lines, 132KB)
- **No build step**: Zero npm, zero node_modules
- **Fonts**: Cormorant Garamond (serif) + Outfit (sans) via Google Fonts
- **Images**: Unsplash + Pexels (external, lazy-loaded)
- **Email**: FormSubmit.co → hola@8998.co
- **Deploy**: Vercel (static, 3s deploy)

## Production
- **URL**: https://89clothing.vercel.app
- **GitHub**: zsoist/89Clothing (branch: claude/create-web-page-structure-Q4lds)
- **Vercel project**: 89clothing (prj_W47hWdlnkuExVb5U17AhHgZUZOfM)

## Sections v2 (8 sections — Apr 22 2026 redesign per Eduardo brief)
1. Hero (split layout, light bg, 2 CTAs)
2. Drop 01 / Producto (4 product cards: Negro, Blanco, Navy, Oliva seco)
3. Bundles (4 bundles with color dots)
4. Por qué la repites (3 reason cards)
5. Comparativa (table: 8998 vs básica promedio, 8 attributes)
6. Acceso anticipado (email capture with 3 benefits, FormSubmit.co)
7. Confianza operativa (4-item horizontal bar)
8. FAQ (accordion, 3 questions)

## Interactive Elements
- Countdown timer (fixed: May 1, 2026)
- Quick view modal per product
- Size guide modal (cm measurements)
- Exit intent popup (email capture)
- Wishlist (localStorage)
- Share (WhatsApp, Twitter, copy link)
- FAQ accordion
- Scroll progress bar
- Cookie consent banner
- Referral link generator

## Deploy
```bash
cd /Volumes/SSD/work/forge-projects/89Clothing
vercel deploy --prod --yes   # 3s deploy, static HTML
```

## Git Identity
```bash
git config user.name "zsoist"
git config user.email "zsoist@users.noreply.github.com"
```
Branch: `claude/create-web-page-structure-Q4lds` (not main!)

## Design Direction (v2 — Apr 22 2026)
- Palette: light warm (hueso #f5f0e8, bg2 #ede8de, text #1a1a1a, accent navy #1a2744, oliva #6b6b3f)
- **Oliva used ONLY for product card color swatch and bundle dot — NOT as UI decoration**
- Mobile-first. Every section resolves at 390px. Quick view always visible on touch (no hover-only)
- Typography: Outfit primary everywhere. Cormorant only for hero H1.
- NO: cursor dot, parallax, counters, social ticker, manifesto, editorial sections
- YES: scroll progress, nav scroll, hamburger, FAQ accordion, email form, quick view modal, size guide, exit popup, cookie, sticky mobile CTA, back-to-top, WhatsApp float
- Copy is FINAL per Eduardo brief Apr 21 — do not change framing or wording without explicit approval
- "Una buena camiseta debería resolver más de una vez." — central thesis, do NOT change

## Pitfalls
- WhatsApp number is placeholder (`wa.me/message/8998CO`) — needs real number (TODO in code)
- Legal pages (Términos, Privacidad, Envíos, Devoluciones) are "próximamente" — not created yet
- TikTok link is placeholder
- Video section is "coming soon" — placeholder image with toast
- Branch is NOT main — push to `claude/create-web-page-structure-Q4lds`
- Exit popup form was missing action — fixed 2026-04-07 (FormSubmit.co)
- Countdown was hardcoded to 30d from page load — fixed to May 1, 2026

## QA Results (2026-04-07)
11 issues found and fixed:
- Countdown → fixed date (was relative)
- Size guide modal → verified working
- Exit popup form → action added
- 24 images → loading="lazy" + decoding="async" + crossorigin
- Footer links → aria-disabled
- Twitter meta tags added
- Canonical URL added (https://8998.co)
- theme-color meta tag added
- All buttons have aria-labels
- Hero image has fetchpriority="high"
- Zero console errors
