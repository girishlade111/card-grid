# Card Grid

A responsive fashion-collection card grid built with Next.js — image cards with titles, subtitles, and color-coded "New" badges, rendered in a clean responsive grid with dark-mode support and smooth hover effects.

> Component based on [Kokonut UI](https://kokonutui.com/) `card-08`; originally generated with [v0.app](https://v0.app), then refined and documented.

## Features

- 🖼️ **Responsive card grid** — 1 → 2 → 3 → 4 columns (mobile → desktop)
- 🏷️ **Color-coded badges** — pink / indigo / orange variants
- 🌙 **Dark / light mode** toggle (next-themes)
- ✨ Glassmorphism card styling with hover lift and border glow
- 🔗 Cards link out (opens in new tab) via `next/link`
- 🖼️ Optimized remote images with `next/image` (unoptimized for static export)
- 📦 Reusable, typed components: `CardGrid` + `Card08`

## Tech Stack

- [Next.js](https://nextjs.org/) 15 (App Router, static export)
- [React](https://react.dev/) 19
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) 3 + `tailwindcss-animate`
- [Lucide React](https://lucide.dev/) icons
- [next-themes](https://github.com/pacocoursey/next-themes) for theming

## Quick Start

### Prerequisites

- Node.js 18+ and npm

### Install & run

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Build (static export)

```bash
npm run build
```

The fully static site is emitted to `out/` and can be hosted on any static host (Cloudflare Pages, GitHub Pages, Netlify, Vercel).

## Project Structure

```
card-grid/
├── app/
│   ├── page.tsx                  # Demo page — sample collection data
│   ├── layout.tsx                # Root layout + theme provider
│   └── globals.css
├── components/
│   ├── kokonutui/
│   │   ├── card-grid.tsx         # Grid section component
│   │   └── card-08.tsx           # Single card component (image + badge + text)
│   └── theme-provider.tsx
├── lib/
│   └── utils.ts                  # cn() class-name helper
├── public/                       # Placeholder assets
├── next.config.mjs               # output: 'export', unoptimized images
└── tailwind.config.ts
```

## Usage

Pass your own items to the grid:

```tsx
import CardGrid from "@/components/kokonutui/card-grid"

<CardGrid
  gridTitle="My Collections"
  items={[
    {
      title: "Summer Line",
      subtitle: "Fit with the latest trends",
      image: "https://example.com/photo.jpg",
      badge: { text: "New", variant: "orange" },
      href: "https://example.com",
    },
  ]}
/>
```

## Environment Variables

None required — all data is static/sample.

## Deployment

The app is a **static export** (`output: 'export'`), so it deploys to any static host:

- **Cloudflare Pages** — point the build output at `out/`
- **GitHub Pages / Netlify / Vercel** — same, serve the `out/` directory

No server, no API routes, no secrets needed.

## Notes

- Sample images are hot-linked from `assets.lummi.ai` / `lummi.ai` demo URLs — replace with your own assets for production use.
- Lint and TypeScript errors are ignored during builds (v0 default).

---

Built by Girish Lade · [ladestack.in](https://ladestack.in)
