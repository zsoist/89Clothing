# 8998 — LLM Reference (AI-First Context)
<!-- This file is the canonical brief for any AI that edits this codebase. -->
<!-- Last updated: 2026-04-22 | Version: 2.0 -->

## What this project is
Homepage for **8998**, a Colombian t-shirt brand launching **Drop 01**.
Single HTML file. No framework. No build step. Deployed on Vercel as a static page.

**Production**: https://89clothing.vercel.app
**GitHub**: zsoist/89Clothing (branch: `claude/create-web-page-structure-Q4lds`)
**Contact**: hola@8998.co | @8998.co on Instagram

---

## Brand brief (final — Eduardo Arenas, Apr 21 2026)

### Central thesis
> Una buena camiseta debería resolver más de una vez.

**Do not change this line.** It is the load-bearing copy for the entire page.

### What we're selling
A t-shirt that:
- Looks good without effort
- Feels fresh (180g combed cotton)
- Functions in real daily use
- Repeats well (maintains quality with washing)
- Becomes "the one you reach for"

### What we are NOT
- Not a premium basics brand
- Not a luxury brand
- Not a founder story brand
- Not a sustainability brand
- Not a manifesto brand

### Target person
Colombian man, 22–40. Wants to look good without overthinking it. Values pieces he can repeat with confidence. No logos, no hype, no excess.

### Language rules (STRICT)
- Spanish: Bogotá-natural, neutral, sober, clear
- No agency language
- No luxury clichés
- Never use: premium, sofisticado, lujo silencioso, atemporal, esenciales de lujo, statement, cápsula, armario, curado, elevar tu estilo
- If in doubt: simpler, shorter, more direct

### Tone
Sober · Clear · Serious · Contained · Commercial (not editorial)

---

## Page structure (v2 — 8 sections only)

| # | Section | Purpose |
|---|---------|---------|
| 1 | Hero | First impression + 2 CTAs |
| 2 | Drop 01 / Producto | 4 product cards, price visible |
| 3 | Bundles | 4 bundle options |
| 4 | Por qué la repites | 3 proof cards |
| 5 | Comparativa | 8998 vs básica promedio, 8 attributes |
| 6 | Acceso anticipado | Email capture with 3 benefits |
| 7 | Confianza operativa | 4-item trust bar |
| 8 | FAQ | Accordion (3 questions) |

**Do not add sections outside this structure** without Eduardo's explicit approval.

### Sections that were removed (do NOT re-add)
- Founder / historia
- Timeline / proceso
- Testimonios
- Valores
- Lookbook como bloque protagonista
- Bloque Colombia como sección principal
- Contador de seguidores / animado
- Manifesto
- Behind the scenes
- Instagram feed grid
- Press / As seen in
- Referral program
- Colombia map
- Packaging
- Video placeholder (as section)
- Color stories
- Care instructions

---

## Visual design rules

### Palette
```css
--bg:      #f5f0e8;   /* hueso/marfil cálido — primary background */
--bg2:     #ede8de;   /* slightly darker — sections, trust bar */
--card:    #ffffff;   /* clean white — product cards, modals */
--surface: #f9f6f0;   /* mid tone — featured sections */
--border:  rgba(26,26,26,.10);
--border2: rgba(26,26,26,.18);
--text:    #1a1a1a;   /* negro carbón — body text */
--dim:     rgba(26,26,26,.6);  /* subtext */
--muted:   rgba(26,26,26,.38); /* hints, labels */
--navy:    #1a2744;   /* primary accent — CTAs, links, headers */
--oliva:   #6b6b3f;   /* ONLY for product swatch / bundle dot */
```

### Typography
- **Primary font**: Outfit (300, 400, 500, 600) — ALL body, buttons, labels, most headings
- **Serif**: Cormorant Garamond (300, 400) — ONLY for Hero H1. Nowhere else.
- Do not add more font weights or families.

### Key rules
- `--oliva` is ONLY a product/bundle color indicator. Never use as UI decoration, button, or section accent.
- `--navy` is the primary action color. All primary buttons use `var(--navy)` background.
- Do not add heavy borders, box shadows, or dramatic gradients.
- Mobile-first. Design and test at 390px wide first.
- No excess vertical whitespace "for luxury effect". Sections should be tight.

---

## Product catalog (Drop 01)

| Color | CSS class | Description | Image |
|-------|-----------|-------------|-------|
| Negro | `.color-negro` | El más fácil de usar. | pexels/8532616 |
| Blanco | `.color-blanco` | El más limpio. | pexels/5746087 |
| Navy | `.color-navy` | El más sobrio. | unsplash/1542219550 |
| Oliva seco | `.color-oliva` | Aporta identidad sin salirse de la lógica del esencial. | unsplash/1618354691792 |

**Price**: $89.900 COP (all colors, same price)
**Status**: Pre-launch. Email capture only. No cart/checkout yet.

---

## Bundle catalog (Drop 01)

| Bundle | Colors | Description |
|--------|--------|-------------|
| Siempre bien | Blanco + negro | Los dos más fáciles de usar |
| La primera base | Negro + blanco + navy | Tres colores que resuelven sin complicar |
| Negro fijo | Triple negro | Para quien ya sabe cuál va a repetir más |
| Con intención | Negro + oliva seco | Una base segura con algo más de intención |

**Bundle copy is final. Do not rename without Eduardo's approval.**

---

## Technical reference

### Stack
```
Single file: index.html (1,226 lines, ~73KB)
No build step, no npm, no node_modules
Fonts: Google Fonts (Outfit + Cormorant Garamond)
Images: Unsplash + Pexels (lazy loaded, placeholder until real product photos)
Email: FormSubmit.co → hola@8998.co
Deploy: Vercel static (vercel deploy --prod --yes)
```

### Interactive components
| Component | JS function | Notes |
|-----------|-------------|-------|
| Quick view modal | `openModal(key)` / `closeModal()` | Uses PRODUCTS{} data object |
| Size guide modal | `openSizeGuide()` / `closeSizeGuide()` | Standard table |
| FAQ accordion | inline event listener | Closes others on open |
| Email form | FormSubmit.co via fetch | Toast on success |
| Exit intent popup | `mouseleave` event | `8998-exit-seen` localStorage flag |
| Cookie bar | `8998-cookie-consent` localStorage | Shows after 2.2s |
| Sticky mobile CTA | `stickyCta` div | Shows after hero scroll |
| Scroll progress | `scrollProgress` div | Updates on scroll |
| Reveal animations | IntersectionObserver | `.reveal` → `.visible` |
| Back to top | `btt` button | Shows after 400px scroll |

### Deploy
```bash
cd /Volumes/SSD/work/forge-projects/89Clothing
git add index.html && git commit -m "description"
git push origin claude/create-web-page-structure-Q4lds
vercel deploy --prod --yes
# URL: https://89clothing.vercel.app
```

### Pitfalls
- Branch is NOT main: always push to `claude/create-web-page-structure-Q4lds`
- WhatsApp number is placeholder (`wa.me/message/8998CO`) — needs real number
- Legal pages (Términos, Privacidad, Envíos, Devoluciones) not created yet
- Images are stock (Unsplash/Pexels) — replace with real product photography before launch
- FormSubmit.co requires first form submission manually confirmed by email owner
- `vercel deploy --prod --yes` requires prod flag — preview env vars may differ

---

## What NOT to do
1. Do not re-add any of the removed sections
2. Do not change the central thesis copy
3. Do not use `--oliva` as a UI/decorative color
4. Do not switch back to dark palette
5. Do not add Cormorant Garamond to body text or section headings
6. Do not make the page more editorial, more aspirational, or more "brand campaign"
7. If choosing between making it more beautiful vs more effective: **choose effective**

---

## Pending before launch
- [ ] Real WhatsApp number (replace `wa.me/message/8998CO`)
- [ ] Real product photography (all 4 colors, clean shots)
- [ ] Legal pages (Términos y condiciones, Política de privacidad, Envíos, Devoluciones)
- [ ] Payment integration (post-access-list phase)
- [ ] FormSubmit.co first-submission email confirmation
- [ ] Verify countdown date (if re-added — currently removed from hero)
