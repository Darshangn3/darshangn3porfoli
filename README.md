# Darshan G N — Cybersecurity Portfolio

A modern, responsive portfolio website for Darshan G N, a cybersecurity postgraduate student, showcasing skills, projects, certifications, and contact information to prospective recruiters.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | TanStack Start (React 19 + TanStack Router v1) |
| Build | Vite 7 |
| Styling | Tailwind CSS 4 (app) + inline CSS (portfolio page) |
| Portfolio Page | Standalone HTML/CSS/JS |
| Icons | Font Awesome 6 (CDN) |
| Fonts | Google Fonts — Inter, Space Grotesk |
| Deployment | Netlify |

## Portfolio Sections

- **Hero** — Name, title, profile photo, CTA buttons (View Projects, Download Resume, GitHub, LinkedIn)
- **About** — Bio and key academic stats
- **Skills** — Categorised skill cards (Programming, Security Tools, Cloud, Networking, OS, Database)
- **Projects** — ML-based DDoS detection and Web Application Vulnerability Assessment
- **Hands-on Experience** — Practical skills narrative cards
- **Certifications & Education** — Certificates (Google, 28DIGITAL, Pentagon Space) and degree history
- **Contact** — Email, Phone, GitHub, LinkedIn contact cards

## Local Development

```bash
npm install
npm run dev       # Start dev server on http://localhost:8888
npm run build     # Production build → dist/client
npm run preview   # Preview production build
```

The portfolio is served from `public/portfolio.html` via a Netlify redirect (`/ → /portfolio.html`).

## Static Assets

| File | Purpose |
|------|---------|
| `public/portfolio.html` | Main portfolio page |
| `public/darshan-profile.jpg` | Profile photo |
| `public/darshangn3resume.pdf` | Downloadable resume |
