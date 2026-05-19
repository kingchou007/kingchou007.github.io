# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is Jinzhou Li's personal academic website, hosted via GitHub Pages at `kingchou007.github.io`. It is a static single-page site (no build step, no framework) — just `index.html` and `style.css`.

## Development

Open `index.html` directly in a browser to preview. No build tools, package managers, or dev servers are required.

## Architecture

- **`index.html`** — The entire site lives here: bio, publications, news/misc, blog filter tabs, and all JavaScript
- **`style.css`** — All styles including CSS reset, layout, responsive breakpoints (768px)
- **`images/`** — Active site media (profile photo, project thumbnails, videos)
- **`docs/`** — Static assets like CV PDF
- **`temp_unused/`** — Archived/unused media; not referenced by the live site
- **`hugo/`** and **`blog/`** — Skeleton directories for a planned Hugo blog (currently empty/unused)

### Key Libraries (loaded via CDN)

- **jQuery 3.6.1** + **jQuery UI 1.13.2**
- **Isotope** — Powers the filterable grid layout for Publications / Misc / Blog tabs
- **imagesLoaded** — Ensures Isotope layout updates as images load
- **marked.js** — Markdown parser (included but not actively used yet)

### How Content Filtering Works

The filter buttons (`#filters .button`) use `data-filter` attributes (`.publication`, `.misc`, `.blog`) to toggle Isotope grid visibility. Each content item has a corresponding CSS class and `data-category` attribute. The active filter is persisted in `localStorage`.

### Adding a New Publication

Add a new `<div class="list-item publication" data-category="publication">` block inside `#main-highlights` in `index.html`. Follow the existing pattern: `.thumbnail` (image/video) + `.project-description` (title, authors, venue, links). The author's name is bolded+underlined with `<b><u>Jinzhou Li</u></b>`.

### Adding a News/Misc Item

Add a `<div class="list-item misc" data-category="misc">` with a `<p class="date">` and `<span>` for the content, following existing entries.

## Conventions

- Google Tag Manager (`GTM-MWZCW9SM`) is active; the older gtag.js snippet is commented out
- Font: Asap (Google Fonts)
- Primary text color: `#150c21`; link color: `rgb(20, 110, 190)`; muted/date color: `#a0a8b0`
- Oral/highlight styling uses `color: #f07c6a`
