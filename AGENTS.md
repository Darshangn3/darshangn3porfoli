# AGENTS.md

## Project Overview

Cybersecurity portfolio website for Darshan G N. The main user-facing portfolio is a **standalone static HTML page** (`public/portfolio.html`) served at `/` via a Netlify redirect. The underlying TanStack Start app remains functional for any future dynamic routes (e.g., `/resume`, `/contact`, `/projects`, `/blog/:slug`).

## Architecture

```
public/
  portfolio.html          ← Main portfolio (HTML/CSS/JS, no framework dependency)
  darshan-profile.jpg     ← Profile photo
  darshangn3resume.pdf    ← Resume download
src/
  routes/                 ← TanStack Start routes (not used for homepage)
  components/             ← React components (Radix UI + Tailwind)
  lib/                    ← Hooks and utilities
netlify.toml              ← Redirect: / → /portfolio.html (force=true)
```

## Key Directories

| Path | Purpose |
|------|---------|
| `public/portfolio.html` | Entire portfolio in a single self-contained HTML file |
| `public/` | Static assets served directly by Netlify CDN |
| `src/routes/` | TanStack file-based routes (not the portfolio homepage) |
| `content/` | Content Collections markdown (jobs, education, blog, projects) |
| `src/components/ui/` | Radix UI-based primitive components |

## Routing Decision

The homepage (`/`) is served as a static HTML file rather than a TanStack SSR route. This was intentional: the portfolio is a pure HTML/CSS/JS document that loads faster with no SSR overhead. The Netlify redirect (`force = true`) intercepts `/` before the TanStack function handles it.

## Coding Conventions

- **Portfolio page**: Vanilla HTML, inline `<style>`, vanilla JS — no build step dependency
- **TanStack routes**: React, TypeScript strict mode, `@/` path alias for `src/*`
- **Styling**: Tailwind CSS 4 for TanStack components; CSS custom properties + Flexbox/Grid for the portfolio page
- **Icons**: Font Awesome 6 (CDN) in portfolio; Lucide React in TanStack components

## Environment Variables

| Variable | Purpose |
|----------|---------|
| `ANTHROPIC_API_KEY` | AI resume assistant (ResumeAssistant component) |
| `OPENAI_API_KEY` | Alternative AI provider |
| `GEMINI_API_KEY` | Alternative AI provider |

## Non-obvious Decisions

- `public/portfolio.html` is named `portfolio.html` (not `index.html`) to avoid collision with Vite's own entry point. The Netlify redirect rewrites `/` to `/portfolio.html` with `force = true` so the CDN serves the static file directly.
- Profile photo uses `object-position: top center` to ensure the face is always visible regardless of container crop.
- The resume download button uses the HTML `download` attribute to force a file download rather than in-browser PDF rendering.
