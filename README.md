# Maison Vell — Runway Depth Lookbook

An editorial, full-viewport fashion lookbook. Drag, scroll, or use the arrow keys to move through the runway, with synchronized product cards and a cart counter.

## Requirements

- Node.js 20.19 or newer (required by Vite 8)
- npm (included with Node.js)

## Run locally

Open a terminal in the project folder (the folder containing `package.json`) and run:

```bash
npm install
npm run dev
```

Open the URL printed by Vite. The development server is configured for [http://localhost:3000](http://localhost:3000).

To make and preview a production build:

```bash
npm run build
npm run preview
```

## Project structure

```text
index.html       Main lookbook markup, styles, and interactions
vite.config.ts   Vite, React, and Tailwind plugin configuration
package.json     Dependencies and npm scripts
src/             React starter files (not used by the current HTML lookbook)
metadata.json    AI Studio metadata
tsconfig.json    TypeScript configuration
```

## Available scripts

- `npm run dev` — Start the local development server on port 3000.
- `npm run build` — Compile the production site into `dist/`.
- `npm run preview` — Serve the production build locally.
- `npm run lint` — Check TypeScript files with `tsc --noEmit`.

## Controls

- Drag or swipe across the runway to move between looks.
- Scroll to scrub through the collection; movement snaps to a look when scrolling stops.
- Use the arrow keys to move between looks.
- Click a model to focus that look.
- Use the heart and plus buttons on product cards to save items and update the cart count.
