# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio/resume website for Vanshil Shah, hosted on GitHub Pages at `vanshilshah97.github.io`. This is a purely static site — no build system, no package manager, no bundler. Files are served directly by GitHub Pages.

## Development

To preview locally, serve the root directory with any static file server:
```
python3 -m http.server 8000
```
Then open `http://localhost:8000`. There is no build step, linting, or test suite.

Deploying is done by pushing to the `master` branch — GitHub Pages serves from it automatically.

## Architecture

**Main page** (`index.html`, ~3,200 lines): Single-page portfolio using a table-based responsive layout (max-width 800px). Contains inline JavaScript for dark/light theme toggling with `localStorage` persistence. Sections cover work experience, research papers, projects, and referenced NeRF papers.

**Stylesheet** (`stylesheet.css`): Shared CSS using Google Fonts (Lato). Handles responsive layout, dark mode colors, and image hover transitions.

**Research project pages** (`mipnerf/`, `mipnerf360/`): Standalone project showcase pages with their own Bootstrap 3.3.5 + jQuery stack, CodeMirror for BibTeX citation display, and separate CSS/JS/image assets.

**Assets** (`images/`): ~220 media files (PNG, JPG, GIF, MP4, PDF) including project screenshots, logos, and resume PDF. `data/` holds `.bib` bibliography files and research documents.

## Key Technical Details

- Google Analytics is integrated via Google Tag Manager (ID: `G-JEQ1SX4MS7`)
- Dark mode toggle uses a button that switches CSS variables and persists choice in `localStorage`
- External libraries are loaded from CDNs (Font Awesome 4.4.0, jQuery 1.11.3, Bootstrap 3.3.5)
- The `images/` directory is large (~570MB); avoid committing unnecessary media files
