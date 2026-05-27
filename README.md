# FutureBridge Solutions Limited — Website

A professional, single-page business website for **FutureBridge Solutions Limited**, built with **plain HTML, CSS, and JavaScript**. No build step, no dependencies, no framework — just static files hosted on **GitHub Pages**.

**Live site:** https://kahuhu25.github.io/Kahuhuwebsite/
**Repository:** https://github.com/kahuhu25/Kahuhuwebsite

## What's inside

```
Kahuhuwebsite/
├── .github/workflows/
│   └── pages.yml         # Automated GitHub Pages deployment
├── assets/
│   └── favicon.svg       # SVG favicon
├── index.html            # Main page (Home, About, Services, Projects, Contact)
├── 404.html              # Custom 404 page
├── styles.css            # All styling (responsive, mobile-first)
├── script.js             # Nav, scroll effects, reveal animations
├── .nojekyll             # Tells GitHub Pages to skip Jekyll processing
├── robots.txt            # Crawler hints
├── .gitignore
└── README.md
```

## Features

- Single-page design with smooth scrolling between sections
- Sticky header with active-section nav highlighting
- Fully responsive (mobile, tablet, desktop)
- Accessible: semantic HTML, skip-link, ARIA labels, focus styles, `prefers-reduced-motion` support
- Reveal-on-scroll animations using `IntersectionObserver`
- Custom 404 page
- Self-hosted Google Fonts (Inter + Source Serif 4) loaded via `<link>`
- Zero dependencies — works offline once cached

## Run locally

You can just double-click `index.html` to open it in your browser. For an even better experience (correct routing for `404.html`, etc.), serve it with a tiny local server:

```bash
# Option 1: Python (built-in on most systems)
python -m http.server 8000

# Option 2: Node (if installed)
npx serve .
```

Then open <http://localhost:8000>.

## Deployment

This repo deploys automatically via **GitHub Actions** (see `.github/workflows/pages.yml`).

### First-time setup (one-time, in the GitHub UI)

1. Go to **Settings → Pages** in the repo.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. That's it. Every push to `main` will rebuild and deploy the site automatically.

> The workflow uses `actions/configure-pages@v5` with `enablement: true`, so on first run it will try to auto-enable Pages for the repo. If your account requires manual enablement, follow the two steps above.

### Updating the site

Just edit files locally and push:

```bash
git add .
git commit -m "Update content"
git push
```

The deploy takes ~30–60 seconds. You can watch the run under the **Actions** tab.

## Customizing

All content is in `index.html` — just edit the text. Common customizations:

| What | Where |
| --- | --- |
| Company name & tagline | `index.html` — `<title>`, hero `<h1>`, footer |
| Colors / theme | `styles.css` — `:root` CSS variables at the top |
| Services | `index.html` — the `<section id="services">` block |
| Projects | `index.html` — the `<section id="projects">` block (current names are placeholders) |
| Partner logos | `index.html` — `<ul class="logo-row">` (currently placeholder names) |
| Contact email | `index.html` — search for `hello@futurebridgesolutions.com` |
| Favicon | replace `assets/favicon.svg` |

### Quick color tweak

Open `styles.css` and edit the `:root` block:

```css
:root {
  --brand: #0b1f3a;    /* primary dark color */
  --brand-2: #1e63ff;  /* accent / link blue */
  --accent: #ffb547;   /* highlight gold */
}
```

## Notes about GitHub Pages

- The `.nojekyll` file tells Pages **not** to run Jekyll, which is what we want for a plain static site. Without it, files starting with `_` may be ignored.
- Relative links (`href="styles.css"`) work correctly under the repo subpath (`/Kahuhuwebsite/`).
- The custom `404.html` is automatically served by GitHub Pages for unknown URLs.

## License

© FutureBridge Solutions Limited. All rights reserved.
