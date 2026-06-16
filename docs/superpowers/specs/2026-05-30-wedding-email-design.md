# Wedding Invitation Email — Design Spec
**Date:** 2026-05-30  
**Project:** WAM_Mail  
**Status:** Approved

---

## Overview

A single, purely informational HTML email sent to wedding guests. The email replicates the aesthetic of the physical wedding invitation — blush, cream, gold, elegant typography — and provides all logistical details guests need for the day.

No RSVP or interactive elements. No external links except Google Maps.

---

## Design System

### Colors
| Variable | Hex | Usage |
|---|---|---|
| Cream background | `#FAF6F0` | Full email background and content area |
| Blush pink | `#F4DCD6` | Header and footer decorative band |
| Charcoal | `#2B2B2B` | All body text |
| Gold | `#D4AF37` | Divider lines, map links, ornaments |

### Typography
| Role | Font | Style | Usage |
|---|---|---|---|
| `font-serif` | Cormorant Garamond | Uppercase, wide letter-spacing | Bride & groom names |
| `font-script` | Great Vibes | Natural flow | "Tešíme sa na Vás" header |
| `font-sans` | Lato | Regular / Small Caps | Section labels, body text, date |

Fonts loaded via Google Fonts embed in `<head>`.

---

## Content

### Bride & Groom
- **Names:** ANETA & MAROŠ

### Event Details
| Section | Content |
|---|---|
| Date | Sobota, 13. jún 2026 |
| Ceremony | 14:00 · Kostol v Nižnej Šebastovej |
| Ceremony map | https://maps.app.goo.gl/NSPS5DX52Mi8tGUy8 |
| Transport | Po obrade bude pre hostí zabezpečený odvoz autobusom priamo k svadobnej sále. Miesto stretnutia: pri kostole. |
| Reception | ~15:30 · Koňareň |
| Reception map | https://maps.app.goo.gl/g6idJ7YdwRtB57GL6 |

---

## Layout Structure

```
┌─────────────────────────────────────┐
│  [blush pink band]                  │
│  ─── gold ornament line ───         │
│  ANETA & MAROŠ          (serif)     │
│  "Tešíme sa na Vás"     (script)    │
│  ─── gold ornament line ───         │
│  [blush pink band]                  │
├─────────────────────────────────────┤
│                                     │
│  Sobota, 13. jún 2026   (serif)     │
│                                     │
│  ─── gold divider ───               │
│                                     │
│  OBRAD                  (sans/caps) │
│  14:00                              │
│  Kostol v Nižnej Šebastovej         │
│  📍 Zobraziť na mape    (gold link) │
│                                     │
│  ─── gold divider ───               │
│                                     │
│  DOPRAVA                (sans/caps) │
│  Miesto stretnutia pri kostole.     │
│  Po obrade autobus priamo k sále.   │
│                                     │
│  ─── gold divider ───               │
│                                     │
│  HOSTINA                (sans/caps) │
│  ~15:30                             │
│  Koňareň                            │
│  📍 Zobraziť na mape    (gold link) │
│                                     │
├─────────────────────────────────────┤
│  [blush pink band]                  │
│  Tešíme sa na Vás · Aneta & Maroš  │
└─────────────────────────────────────┘
```

---

## Technical Notes

- **Format:** Single self-contained HTML file (`email.html`)
- **Email client safety:** Table-based layout for Outlook compatibility; no CSS Grid/Flexbox
- **Max width:** 600px centered, works on mobile
- **Map links:** Styled as `color: #D4AF37; text-decoration: none;` inline text links with "📍 Zobraziť na mape" label
- **No images** (except optional background color blocks via table cell backgrounds) — avoids broken images in clients that block them
- **Inline CSS** throughout for maximum email client compatibility

---

## Out of Scope

- RSVP functionality
- Multi-language versions
- External web page / microsite
- Animated elements
