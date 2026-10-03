# Silver Sniffle

Static single-page website skeleton. Content and visual design get added later.

## Requirements

- Plain HTML + CSS only. No frameworks, no build step, no package manager.
- Vanilla JS only where needed, kept minimal. Currently: copyright year, mobile menu toggle, active menu link.
- Single page; top navigation links to in-page sections (`#home`, `#about`, `#services`, `#contact`).
- Sticky header; hamburger toggle below 768px. Without JS the menu stays visible.
- Smooth scrolling via CSS (`scroll-behavior`), disabled under `prefers-reduced-motion`.
  Sections use `scroll-margin-top` so the sticky header doesn't cover them.
- Responsive: must work at phone width (~375px) with no horizontal scroll.
- CSS is structural; colors, fonts and spacing live as variables in `:root` in `css/style.css`.
- Dark mode is automatic via `prefers-color-scheme` (no manual toggle). Fonts: system stack only.
- The menu link of the section in view gets `aria-current` (small IntersectionObserver in `js/main.js`).
- Placeholder copy is lorem ipsum until real content is provided.
- Footer: copyright only. The year is set by JS, with a static fallback year in the HTML.
- Page language English (`lang="en"`), basic meta only (title, description, favicon).

## Structure

```
index.html
css/style.css
js/main.js
assets/        images, favicon
```

## Viewing and deployment

The site is hosted on GitHub Pages: https://primal-stoic-ark.github.io/silver-sniffle/

- `.github/workflows/pages.yml` deploys on every push to `main` (and, temporarily, to
  `claude/sweet-volta-okjrqi`, the current default branch). It can also be run by hand.
- Only `index.html`, `css/`, `js/` and `assets/` are published.
- Actions are pinned to full commit SHAs (with the version in a comment). When updating
  one, look up the new tag's SHA from the official `actions/*` repo.
- Asset paths must stay relative (`css/style.css`, not `/css/style.css`), because the site
  is served from the `/silver-sniffle/` subpath.

Before pushing, check desktop (1280px) and mobile (375px) widths in headless Chromium:
no console errors, no horizontal scroll, and the mobile menu opens and closes.

Local viewing: `python3 -m http.server 8000`, then http://localhost:8000.
