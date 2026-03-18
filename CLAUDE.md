# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal portfolio/blog website for Linning Xu, a Computer Vision researcher (Neural Rendering, 3D Gaussian Splatting, Embodied Intelligence). The site is deployed via GitHub Pages from the `docs/` directory.

## Development

There is no build system in this repository — the `docs/` directory contains hand-authored HTML pages plus compiled SvelteKit/Vite output in `docs/app/immutable/` (pre-built artifacts, do not edit). All content changes happen by editing the HTML files directly.

**To preview changes:** Open `docs/index.html` or any HTML file in a browser, or run a local HTTP server:
```
python3 -m http.server 8000 --directory docs
```

**To deploy:** Push to `master`; GitHub Pages serves from `docs/`.

## Repository Structure

```
docs/
├── index.html       # Main portfolio page — project gallery, starfield, filtering
├── blog.html        # Blog/articles (CV, NeRF, robotics, AI topics)
├── bookshelf.html   # Reading collection
├── food.html        # Food diary
├── map.html         # World map of visited places
├── moodboard.html   # Visual mood board
├── gpt_imgs/        # Project thumbnail images
├── assets/          # Fonts and sticker graphics
└── app/immutable/   # Compiled SvelteKit output — do not edit
```

## Architecture

Each HTML page is self-contained with embedded CSS and JavaScript. No external build pipeline is involved for the static pages.

**Data is embedded directly in each HTML file** as JavaScript arrays — e.g., portfolio projects in `index.html` and blog posts in `blog.html` are plain JS objects with fields like `date`, `tags`, `title`, `excerpt`, and `content`.

**Key interactive features in `index.html`:**
- Canvas-based starfield animation with tweening
- Project gallery with tag-based filtering system
- Modal overlays for project details

**Fonts** are loaded from Google Fonts (Inter, JetBrains Mono, Cormorant Garamond, DM Sans).

## Common Tasks

- **Add a new project:** Edit the projects array in `docs/index.html`, add a thumbnail to `docs/gpt_imgs/`.
- **Add a blog post:** Edit the posts array in `docs/blog.html`.
- **Update travel map:** Edit the locations data in `docs/map.html`.
