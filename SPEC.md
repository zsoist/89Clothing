# 8998 — Product Specification

## Problem
Colombian men lack access to high-quality, well-fitting basic t-shirts at a fair price. Most options are either cheap fast-fashion (poor fit, degrades quickly) or overpriced imported brands.

## Solution
8998 offers essential t-shirts made in Colombia with:
- 180gsm combed cotton (fresh for tropical climate)
- Reinforced double-stitch collar (doesn't deform)
- Considered body-fit (not boxy, not tight)
- **4 colors** (v2): Negro, Blanco, Navy, Oliva seco
- $89,900 COP (~$22 USD) — precio acorde a lo que entrega

## Target User
Colombian men 22-40 who care about how they look but don't follow fashion trends. They want basics that work every day — for work, social, casual.

## Business Model
- Direct-to-consumer (no retail markup)
- Drop model (limited production runs → urgency)
- Email-first launch (priority access list)
- Instagram as primary brand channel (@8998.co)
- WhatsApp for customer support

## Success Criteria
- [x] ✅ Landing page live with email capture
- [x] ✅ 4 product variants displayed with pricing (v2 adds Oliva seco)
- [x] ✅ Mobile-first responsive design
- [x] ✅ Size guide with measurements
- [x] ✅ FAQ section
- [x] ✅ Bundles section (4 bundles)
- [x] ✅ Comparison table (8998 vs básica promedio)
- [x] ✅ Commercial v2 redesign (light palette, 8 sections, per Eduardo brief Apr 21)
- [ ] Real WhatsApp number connected
- [ ] Legal pages (terms, privacy, shipping, returns)
- [ ] Payment integration (when Drop 01 launches)
- [ ] Real product photography (replace stock photos)
- [ ] Video content (Drop 01 launch)

## Architecture
Single HTML file, zero dependencies. Deployed as static site on Vercel.
No backend needed until payment integration (Drop 01 launch).
