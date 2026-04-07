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

## Key Sections (25 sections, single page)
Hero → Products (Negro/Blanco/Navy, $89.900 COP) → La Idea → Video (coming soon) → Fabric Details → Real Usage → Color Stories → Care → Process → Colombia Trust → Timeline → Founder → Lookbook → Testimonials → Comparison → Values → Guarantee → FAQ → BTS → Packaging → Press (empty) → Instagram → Priority Access (email form) → Referral → Colombia Map

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
