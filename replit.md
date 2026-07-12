# De La Salle John Bosco College (DLSJBC) Website

A modern, elegant redesign of the official school website for De La Salle John Bosco College — a PAASCU-accredited Lasallian school in Bislig City, Surigao del Sur, Philippines.

## Run & Operate

- `pnpm --filter @workspace/dlsjbc run dev` — run the frontend (port auto-assigned)
- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- Frontend: React + Vite + Tailwind CSS
- Routing: Wouter
- Animations: Framer Motion + CSS keyframes + IntersectionObserver
- Forms: react-hook-form + zod
- Icons: lucide-react + react-icons

## Where things live

- `artifacts/dlsjbc/` — main school website (React + Vite)
  - `src/pages/Home.tsx` — homepage with hero, cards, MV&C, events, articles, gallery, map
  - `src/pages/Admissions.tsx` — requirements, procedures, programs, FAQ
  - `src/pages/About.tsx` — history, mission/vision, core values, timeline, administration
  - `src/pages/Articles.tsx` — filterable news & articles grid
  - `src/pages/Contact.tsx` — contact form, info, map
  - `src/components/Navbar.tsx` — sticky glassmorphism nav with dark mode toggle
  - `src/components/Footer.tsx` — full footer with quick links, contact, social
  - `src/components/LoadingScreen.tsx` — branded loading screen with emerald spinner
  - `src/components/ThemeProvider.tsx` — dark mode context + localStorage
  - `src/index.css` — emerald green theme palette (light + dark)
- `artifacts/dlsjbc/public/dlsjbc-logo.png` — official school seal/logo

## Architecture decisions

- Presentation-first: no backend needed — all content is hardcoded static data
- Dark mode via Tailwind `dark:` classes + ThemeProvider context + localStorage
- Scroll reveal animations via IntersectionObserver (no heavy library dependency)
- Floating hero buttons via CSS keyframe animation (.animate-float)
- Hero slideshow and gallery slideshow using React state + CSS opacity transitions

## Product

- **Home**: Fullscreen hero slideshow → quick info cards → mission/vision/core values → events calendar → latest articles → events gallery → campus map
- **Admissions**: Documentary requirements by level, enrollment procedures, college programs, tuition info, FAQ
- **About**: School history, mission & vision, core values, timeline (1950s–2007), administration, campus photos
- **Articles**: Filterable news/blog grid with category tabs (All, Academics, Events, Announcements, Campus Life, Sports)
- **Contact**: Validated contact form, contact info cards, embedded Google Maps

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

- Google Fonts `@import url(...)` must be the VERY FIRST line of index.css (before `@import "tailwindcss"`)
- The school logo is at `artifacts/dlsjbc/public/dlsjbc-logo.png` — served as `/dlsjbc-logo.png` in-app
- No online application or entrance exam at DLSJBC — admissions is face-to-face only
- Replace placeholder images with official school photos when available

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
