# Premium-Hotel-Digital-Menu
Premium Digital Menu and Hospitality Interface

Action: file_editor create /app/memory/PRD.md --file-text "# Maison Lumière — In-Residence Dining PRD

## Original Problem Statement
Create a luxury-tier, mobile-first frontend for a hotel's digital ordering system, designed to mimic
the fluidity of a native mobile application. Technical stack: Tailwind CSS + React. Required:
- Mobile-optimized, masonry-style layout for high-quality food imagery
- Animated category filtering that seamlessly rearranges DOM
- Persistent, sticky order summary bar tracking selected items
- Design mockups and final coded interface with premium brand aesthetic

## User Choices (from ask_human)
- **Scope:** Frontend-only with mock/demo menu data
- **Aesthetic:** User open to all — Warm / Dark / Coastal luxury (let design agent decide)
- **Order flow:** Cart review → Room/Table entry → Send to Kitchen confirmation
- **Imagery / categories:** Defaults (chosen by design agent)

## Architecture
- **Stack:** React 19 + react-router + Tailwind + framer-motion 12 + lucide-react + sonner
- **State:** Single container (`OrderingApp.jsx`) holds `activeCategory`, `cart`, `activeItem`,
  `view` (menu/cart/checkout/confirmed), and `lastOrder`. All sheets driven by `AnimatePresence`.
- **Mock data:** `/app/frontend/src/data/menu.js` — 12 items, 6 categories
- **Brand:** \"Maison Lumière\" · Warm Luxury (Alabaster `#F9F6F0`, Bone `#FFF`, Terracotta `#B85C38`,
  Ink `#2C2A29`). Fonts: Cormorant Garamond (display) + Manrope (body).

## What's Been Implemented — 2026-02 (MVP)
- Sticky glass header with suite label + search + cart icon with animated badge
- Horizontal category chip nav with framer-motion `layoutId` animated indicator pill
- Animated 2-col masonry grid (`items-start` + varying aspect ratios) with `layout` + `AnimatePresence`
  popLayout for smooth category reflow
- Menu cards with dietary badges (Leaf / Wheat-off / Star / Flame) and terracotta signature highlight
- Bottom-sheet item detail modal with quantity selector and add-to-cart
- Sticky glass cart summary bar (slides up when count>0, shows count + subtotal, tap to review)
- Full-screen cart review sheet with qty controls, subtotal + service + total
- Checkout sheet with room/table toggle, number input, notes, order summary
- Confirmation screen with generated order ID + summary + destination, \"Return to menu\"
- Sonner toast on add-to-cart; tactile `active:scale` micro-interactions throughout
- All interactive elements carry `data-testid` for automation

## Testing — Iteration 1 (/app/test_reports/iteration_1.json)
- Frontend: **100% pass** — all 9 flows verified, zero console errors, zero broken images
- No backend to test (frontend-only by choice)

## User Personas
- **Hotel guest in-suite** — wants to order room service at 01:00 without calling
- **Restaurant diner** — wants to browse the menu tableside before flagging a server
- **Bar patron** — curious about the cocktail list

## Prioritised Backlog
### P1 — Next Obvious Upgrades
- Search bar wired up (header search button currently decorative)
- Multi-category view / \"All\" filter
- Favorites (heart) + \"recently ordered\" section
- Item allergen deep-dive / dietary filter chips
- Orders history drawer (requires backend)

### P2 — Luxury Polish
- Localised currency + i18n
- In-suite \"dietary profile\" on first-launch
- Order tracking timeline (preparing → en route → delivered)
- QR onboarding: scan in-room QR → auto-fills Suite number

### P3 — Backend
- FastAPI + MongoDB to persist menu & orders
- Admin console for chef to manage menu + view incoming tickets
- Live kitchen display integration (printer / KDS webhook)
- Payment (Stripe) for non-resident dining

## Next Action Items
- Gather user feedback on current MVP aesthetic before further iteration
- Decide whether to move to full-stack (backend + persistence) or keep as marketing-grade demo
"
Observation: Create successful: /app/memory/PRD.md
