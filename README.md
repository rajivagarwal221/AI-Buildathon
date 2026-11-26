# LuxeCity AI Glow

A luxury salon discovery app for Mumbai, built for an AI buildathon. Browse curated salons, get beauty advice from an AI advisor, find your best-fit stylist with an AI matchmaker, and join a members' club for exclusive pricing.

## Features

| Page | Route | What it does |
| --- | --- | --- |
| Home | `/` | Animated hero, featured salons, how it works, testimonials, club and app download sections |
| Explore | `/explore` | Browse and search salons, with optional live results from Google Places |
| Salon | `/salon/:id` | Salon details, services, prices and durations |
| AI Advisor | `/ai-advisor` | Chat-style beauty advisor |
| AI Matchmaker | `/matchmaker` | Describe what you want and get matched to a salon |
| Membership | `/membership` | Three club tiers (₹999, ₹2,999, ₹7,999) |
| Profile | `/profile` | Your account and bookings |
| About, Contact | `/about`, `/contact` | Brand story and contact form |

## Tech stack

- React 19 + TypeScript, Vite 8, React Router 7
- Tailwind CSS 4, shadcn/ui (Radix primitives), Framer Motion, Lucide icons
- Firebase (auth and data)
- Google Places API (New) for live salon search, with a curated fallback list

## Getting started

```bash
git clone https://github.com/rajivagarwal221/AI-Buildathon.git
cd AI-Buildathon
npm install
cp .env.example .env.local   # add your Firebase config (Places key optional)
npm run dev                  # http://localhost:5173
```

## Scripts

| Command | What it does |
| --- | --- |
| `npm run dev` | Start the dev server |
| `npm run build` | Production build to `dist/` |
| `npm run preview` | Preview the production build |
| `npm run lint` | ESLint |
| `npm run format` | Prettier |

## Project structure

```text
src/
  routes/       one file per page (index, explore, salon.$id, ai-advisor, ...)
  components/   nav, footer, salon card, AI orb, cursor glow, ui/ (shadcn)
  lib/          firebase.ts, salons.ts (data + Places search), utils
  hooks/        use-mobile
```

## Notes

Keep real keys in `.env.local`, which git ignores. Restrict the Google Places key to your site's domain in Google Cloud Console, because Vite puts `VITE_*` values in the browser bundle.
