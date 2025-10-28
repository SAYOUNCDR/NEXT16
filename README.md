# Next.js project — README

This repository contains a Next.js project scaffolded with TypeScript. The README below documents how the project was created, how to run it locally, and a note about enabling Turbopack filesystem caching for development.

## Prerequisites

- Node.js (recommended LTS; e.g. 18, 20)
- npm (or pnpm/yarn if you prefer)

## Create / Install (what I did)

I created the project using the Next.js starter. To create a new project in the current directory you can run:

```bash
# Create the project in the current directory
npx create-next-app@latest ./
```

If you're working with the existing repo, install dependencies:

```bash
npm install
# or
# pnpm install
# yarn install
```

## Run the development server

```bash
npm run dev
# then open http://localhost:3000
```

## Enabling Turbopack filesystem cache (optional)

To enable the Turbopack filesystem cache for faster dev builds, add the experimental flag to your Next.js config.

If your project uses `next.config.js`:

```js
module.exports = {
  experimental: {
    turbopackFileSystemCacheForDev: true,
  },
};
```

If your project uses TypeScript and `next.config.ts` (as this workspace may), use the equivalent:

```ts
import { NextConfig } from 'next';

const nextConfig: NextConfig = {
  experimental: {
    turbopackFileSystemCacheForDev: true,
  },
};

export default nextConfig;
```

Note: Experimental flags may change between Next.js versions. Remove or update this when upgrading Next.

## Project structure (common files)

- `tsconfig.json` — TypeScript configuration
- `next-env.d.ts` — Next.js TypeScript environment types
- `next.config.ts` / `next.config.js` — Next.js configuration (see turbopack note above)
- `package.json` — project scripts and dependencies
- `postcss.config.mjs` — PostCSS config
- `eslint.config.mjs` — ESLint config
- `app/` — application source (Next App Router)
  - `layout.tsx` — root layout
  - `page.tsx` — main page
  - `globals.css` — global styles
- `public/` — static assets (served from `/`)

## Notes

- Static assets placed in `public/` are referenced with `/filename` in the browser.
- If you modify `next.config.ts`/`next.config.js`, restart the dev server to pick up changes.

## Helpful scripts (from `package.json`)

- `dev` — start Next.js dev server
- `build` — production build
- `start` — run production build


