# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Workspace structure

This repository is a Udemy course workspace. All application code lives in the `hookhub/` subdirectory, which has its own `CLAUDE.md` with project-specific guidance. Run all commands from within `hookhub/`.

## hookhub — Next.js app

### Commands

```bash
cd hookhub
npm run dev      # start dev server at http://localhost:3000
npm run build    # production build
npm run lint     # run ESLint
```

No test suite is configured.

### Key constraints

- **Next.js 16.2.6 + React 19.2.4** — breaking changes from older versions. Before writing any Next.js or React code, read the relevant guide in `hookhub/node_modules/next/dist/docs/`. Do not rely on training-data knowledge of Next.js 13–15 APIs.
- **Tailwind CSS v4** — CSS entry point uses `@import "tailwindcss"` (not `@tailwind` directives). Theme customization uses `@theme inline { ... }` blocks in `app/globals.css`, not `tailwind.config.js`.

### Architecture

- **App Router** — all routes live under `hookhub/app/`. Root layout: `app/layout.tsx`; home page: `app/page.tsx`.
- **Fonts** — Geist Sans and Geist Mono loaded via `next/font/google` in `layout.tsx`, exposed as CSS variables (`--font-geist-sans`, `--font-geist-mono`).
- **Styling** — global styles and Tailwind theme configuration in `app/globals.css`.
