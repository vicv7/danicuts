# Handoff: DANI CUTS — Barber Website

## Overview
Full single-page website for **DANI CUTS** — an industrial-style barber shop in Varna, Bulgaria.
The site includes: sticky navigation, hero section, services & pricing, about/story, photo gallery, booking form, and footer.

## About the Design Files
The files in this bundle are **HTML design references** — high-fidelity prototypes showing the intended look, layout, and interactions. They are **not** production code to ship directly.

Your task is to **recreate these designs in your target codebase** (React, Next.js, Vue, or whatever framework fits the project) using its established patterns and libraries. Treat the HTML files as a visual and behavioral spec.

---

## Fidelity
**High-fidelity.** Final colors, typography, spacing, layout, and interactions are all specified. Recreate pixel-precisely using your codebase's stack.

---

## Design System

### Colors
| Token | Hex | Usage |
|---|---|---|
| `bg-primary` | `#080808` | Main page background |
| `bg-secondary` | `#0A0A0A` | Alternate sections (услуги, галерия) |
| `bg-surface` | `#0E0E0E` | Cards, form inputs |
| `bg-footer` | `#060606` | Footer background |
| `text-primary` | `#F0EAE0` | All body text |
| `text-muted` | `rgba(240,234,224,0.42)` | Secondary text |
| `text-dim` | `rgba(240,234,224,0.28)` | Captions, placeholders |
| `accent` | `#C97A2E` | Amber — CTA buttons, prices, labels, accents |
| `border` | `rgba(240,234,224,0.07)` | Subtle dividers |
| `border-accent` | `rgba(201,122,46,0.15)` | Section top borders |

### Typography
| Role | Font | Size | Weight | Letter-spacing |
|---|---|---|---|---|
| Logo / Nav brand | Barlow Condensed | 22px | 900 | 0.22em |
| Hero heading | Barlow Condensed | 168px | 900 | -0.01em |
| Section heading (large) | Barlow Condensed | 80px | 900 | — |
| Section label (small tag) | Barlow Condensed | 11px | 700 | 0.28em |
| Service name | Space Grotesk | 24px | 600 | 0.07em |
| Price | Barlow Condensed | 38px | 700 | — |
| Body text | Space Grotesk | 17–19px | 400 | — |
| Nav links | Space Grotesk | 12px | 400 | 0.1em |
| Labels / captions | Space Grotesk | 11–12px | 400 | 0.15em |

**Google Fonts import:**
```
https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;700;800;900&family=Space+Grotesk:wght@300;400;500;600&display=swap
```

### Spacing
- Section padding (desktop): `96px 120px`
- Section padding (tablet <900px): `64px 40px`
- Section padding (mobile <600px): `48px 24px`
- Column gap: `80px`
- Nav height: `80px`

### Border radius
None — all edges are sharp (industrial aesthetic).

---

## Pages / Sections

### 1. Navigation (sticky)
- `position: sticky; top: 0; z-index: 100`
- Height: 80px
- Background: `rgba(8,8,8,0.96)` + `backdrop-filter: blur(10px)`
- Bottom border: `1px solid rgba(240,234,224,0.06)`
- Layout: flex, space-between
  - **Left:** Logo "DANI CUTS" — Barlow Condensed 900, 22px, `#F0EAE0`, letter-spacing 0.22em
  - **Center:** Links — Услуги / За нас / Галерия / Контакти — Space Grotesk 12px, `rgba(240,234,224,0.38)`, uppercase, letter-spacing 0.1em
  - **Right:** CTA button "ЗАПАЗИ ЧАС" — background `#C97A2E`, white text, Barlow Condensed 700, 13px, letter-spacing 0.2em, padding 14px 32px
- **Mobile (<900px):** Hide center nav links, show only logo + CTA button

### 2. Hero
- `min-height: calc(100vh - 80px)`
- Background: `#080808`
- Subtle scanline overlay: `repeating-linear-gradient(0deg, transparent 0, transparent 3px, rgba(255,255,255,0.006) 3px, rgba(255,255,255,0.006) 4px)`
- Layout: flex row, align-items center, gap 80px, padding 0 120px

**Left column (580px wide):**
- Small amber tag: "— Бръснарница · Варна, България" — 11px, `#C97A2E`, letter-spacing 0.28em, uppercase, margin-bottom 36px
- Heading: "DANI" + line break + "CUTS" — Barlow Condensed 900, 168px, `#F0EAE0`, line-height 0.83
- Amber rule: 52px wide, 3px tall, `#C97A2E`, margin 36px 0 28px
- Tagline: "Прецизни мъжки прически. Бръснене. Без компромис." — Space Grotesk 17px, `rgba(240,234,224,0.44)`, line-height 1.7, max-width 380px
- CTAs (flex row, gap 20px):
  - Primary: "ЗАПАЗИ ЧАС →" — `#C97A2E` bg, white, Barlow Condensed 700, 16px, padding 18px 52px, links to #rezervatsiya
  - Secondary: "ВИЖДАМ УСЛУГИТЕ" — transparent, `rgba(240,234,224,0.42)`, Barlow Condensed 600, 14px, border-bottom `1px solid rgba(240,234,224,0.18)`, links to #uslug
- Phone number below CTAs: `rgba(240,234,224,0.22)`, 13px

**Right column (flex: 1):**
- Full-height image area — replace placeholder with real photo
- Amber corner accents: 52px × 3px lines at all 4 corners (top-left, bottom-right)

**Scroll hint:** Bottom-left of hero — small "Скролни" label with a 36px horizontal rule

**Mobile:** Hide right image column, text goes full width

### 3. Услуги и цени (id="uslug")
- Background: `#0A0A0A`, top border: `1px solid rgba(201,122,46,0.15)`
- Section label: "01 — Услуги и цени"
- Heading: "Какво правим" — 80px

**Services grid:**
- 3 columns desktop, 2 columns tablet, 1 column mobile
- Gap: 1px, background `rgba(240,234,224,0.05)` (creates hairline dividers)
- Each card: background `#0A0A0A`, padding 36px 32px

| Service | BG Name | EN Subtitle | Price |
|---|---|---|---|
| Прическа | Haircut · Класическа или модерна | 25 € |
| Бръснене | Classic Hot Shave | 20 € |
| Комбо | Прическа + Бръснене | 40 € |
| Детска | Kids Haircut · До 12г. | 18 € |
| Брада | Beard Trim + Оформяне | 15 € |
| Линия | Line Up · Edge Up | 10 € |

Card anatomy:
- Name: Space Grotesk 600, 24px, uppercase, `#F0EAE0`, letter-spacing 0.07em
- Subtitle: Space Grotesk 12px, `rgba(240,234,224,0.28)`, letter-spacing 0.06em
- Price: Barlow Condensed 700, 38px, `#C97A2E`

**CTA Strip (below grid, margin-top 64px):**
- Background: `#C97A2E`
- Padding: 40px 56px
- Left: "Готов за нова прическа?" — Barlow Condensed 900, 52px, white
- Right: "ЗАПАЗИ ЧАС →" button — white bg, `#C97A2E` text, Barlow Condensed 900, 16px, padding 20px 56px

### 4. За нас (id="za-nas")
- Background: `#080808`, top border: `1px solid rgba(240,234,224,0.06)`
- Section label: "02 — Историята"
- Heading: "За нас" — 80px

**Layout:** flex row, gap 80px

**Left (flex: 1):**
- 2 paragraphs of story text — Space Grotesk 19px, `rgba(240,234,224,0.62)`, line-height 1.75
- Stats row (flex, border-top/bottom `rgba(240,234,224,0.08)`):
  - "10+" / Год. опит
  - "2 500+" / Доволни клиенти
  - "2020" / Основана
  - Stat number: Barlow Condensed 900, 60px, `#C97A2E`
  - Stat label: 12px, `rgba(240,234,224,0.32)`, uppercase, letter-spacing 0.1em

**Right (420px × 560px):**
- Portrait photo of the barber — replace placeholder
- Amber corner accents (same as hero)

**Mobile:** Hide right image

### 5. Галерия (id="galeriya")
- Background: `#0A0A0A`, top border amber
- Section label: "03 — Галерия"
- Heading: "Нашата работа" — 80px

**Grid:** 3 columns, `grid-auto-rows: 210px`, gap 3px, `grid-auto-flow: row dense`
- 2 cells span 2 rows (portrait orientation) — set `grid-row: span 2`
- 5 cells are single row (landscape)
- Replace all 7 placeholders with real barbershop photos

**Mobile:** 2 columns

### 6. Резервация (id="rezervatsiya")
- Background: `#080808`, top border subtle
- Section label: "04 — Резервация"
- Heading: "Запази своя час" — 80px

**Layout:** flex row, gap 80px

**Left — Booking form (flex: 1):**
- Form fields (all: background `#0E0E0E`, border `1px solid rgba(240,234,224,0.1)`, color `#F0EAE0`, font-size 15px, padding 14px 16px)
- Fields: Три имена + Телефон (2-col grid), Услуга (select), Дата + Час (2-col grid)
- Submit button: full-width, `#C97A2E` bg, white, Barlow Condensed 700, 17px, letter-spacing 0.2em, padding 20px
- Focus state: `border-color: #C97A2E`
- **Success state:** After submit, show confirmation message with "✓ Заявката е изпратена" and a "НОВА РЕЗЕРВАЦИЯ" ghost button

**Right — Info panel (340px):**
- Working hours table
- Contact info (phone, email, address)
- Google Maps embed (replace placeholder)

**Mobile:** Stack form above info panel

### 7. Footer
- Background: `#060606`, top border `rgba(240,234,224,0.06)`
- Padding: 72px 120px 36px
- 4-column flex layout: Logo+tagline | Navigation | Работно време | Социални
- Bottom strip: copyright left, 36px amber rule right

---

## Interactions & Behavior

- **Smooth scroll:** `scroll-behavior: smooth` on `html`
- **Nav links:** Anchor scroll to section IDs (`#uslug`, `#za-nas`, `#galeriya`, `#rezervatsiya`)
- **Booking form:** Client-side validation (required fields), success state on submit (no page reload)
- **Custom scrollbar:** 4px wide, `#C97A2E` thumb, `#080808` track
- **Input focus:** `border-color: #C97A2E`, no outline

---

## Responsive Breakpoints

| Breakpoint | Changes |
|---|---|
| `<900px` | Hide nav links, stack hero/about/booking columns, services → 2 col, hide hero/about images |
| `<600px` | Services → 1 col, reduce hero heading to 86px, reduce section padding |

---

## Assets Needed (replace placeholders)
- Hero photo: full-height, portrait or landscape of barber/studio
- About portrait: portrait of barber "Дани", ~420×560px
- Gallery: 7 barbershop photos (2 portrait format, 5 landscape)
- Google Maps embed for location in Varna

---

## Files in This Bundle
- `DANI CUTS.dc.html` — Complete high-fidelity design prototype (single scrolling page)

---

## Notes for Developer
- All prices are in **€ (Euro)** — Bulgaria adopted the Euro in 2025
- The booking form is currently front-end only — wire it to your backend/booking system (Calendly, custom API, etc.)
- Copy/content (phone, email, address, story text, stats) are placeholders — client will provide final copy
- Gallery images are placeholders — client will provide real photos
- The design uses NO border-radius anywhere (intentional industrial aesthetic)
- Font stack: Barlow Condensed + Space Grotesk from Google Fonts
