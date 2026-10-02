# Silver Sniffle

Static single-page website skeleton. Content and visual design get added later.

## Requirements

- Plain HTML + CSS only. No frameworks, no build step, no package manager.
- Vanilla JS only where needed, kept minimal. Currently: copyright year, mobile menu toggle.
- Single page; top navigation links to in-page sections (`#home`, `#about`, `#services`, `#contact`).
- Sticky header; hamburger toggle below 768px. Without JS the menu stays visible.
- Smooth scrolling via CSS (`scroll-behavior`), disabled under `prefers-reduced-motion`.
  Sections use `scroll-margin-top` so the sticky header doesn't cover them.
- Responsive: must work at phone width (~375px) with no horizontal scroll.
- CSS is structural; colors, fonts and spacing live as variables in `:root` in `css/style.css`.
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

## Previewing changes

After every change to `index.html`, `css/` or `js/`, refresh the private preview artifact:

1. Build a single-file copy in the scratchpad (never commit it):
   - take the `<title>` and the `<body>` contents from `index.html`
     (drop the doctype and the `<html>`, `<head>` and `<body>` wrappers; the viewer adds its own)
   - inline `css/style.css` in a `<style>` tag
   - add `<script>document.documentElement.classList.add('js');</script>` before the body content
   - inline `js/main.js` in a `<script>` at the end
   - title: `Silver Sniffle Skeleton`
2. Publish it with the Artifact tool to the existing URL:
   https://claude.ai/artifact/NuNTrz3BkLnKyLTcUgfm8a
   (pass it as `url` from a new session; read it first, then republish).
3. Give the user the link.

Known preview limits: `mailto:` links may not work inside the viewer.

Before pushing, check desktop (1280px) and mobile (375px) widths in headless Chromium:
no console errors, no horizontal scroll, and the mobile menu opens and closes.

Local viewing: `python3 -m http.server 8000`, then http://localhost:8000.

## Hosting (not decided yet)

The repo is private. GitHub Pages would make the site public and needs a paid plan for
private repos. Cloudflare Pages or Netlify are the alternatives. Until one is chosen,
the artifact preview above is the way to view the site.
