# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is Brendan Glover's personal portfolio website — a single-page, zero-dependency site hosted on GitHub Pages. It is pure HTML/CSS/JavaScript with no build system.

## Deployment

The site is deployed directly via GitHub Pages from the `main` branch. To publish changes, push to `main` — no build step required. The live URL is `https://brendanglover.github.io`.

## Architecture

Everything lives in `index.html` (a single ~830-line file). There is no component system, no bundler, and no framework. Structure within the file:

1. `<head>` — SEO meta tags, Open Graph/Twitter cards, JSON-LD structured data (Person + WebApplication schemas), Google Fonts, Google Analytics (GA4: G-E3YYY6TW7V), inline `<style>` block with all CSS
2. `<body>` — Sections in order: nav → hero → about → experience → projects → blog → contact → footer
3. `<script>` at end of body — all JavaScript (custom cursor, typed animation, scroll progress bar, IntersectionObserver reveal animations, Formspree contact form handler)

## Design System

CSS custom properties defined in `:root`:
- `--bg: #04040a` (dark background)
- `--cyan: #00f5c8` (primary accent)
- `--pink: #ff2d6b` (secondary accent)
- `--yellow: #f5c400` (tertiary)
- `--text: #c8c8e0` (body text)

Fonts: Orbitron (headings), Share Tech Mono (labels/code), Exo 2 (body). The visual theme is dark cyberpunk with glow effects.

## Key Integrations

- **Formspree** (`https://formspree.io/f/mvzvokoo`) — handles the contact form POST
- **Google Analytics** — GA4 tag in `<head>`
- **Google Fonts** — loaded via `<link>` in `<head>`

## Things to Watch Out For

- The JSON-LD structured data in `<head>` must stay in sync with visible content (certifications, job titles, tools listed)
- `sitemap.xml` has a hardcoded `<lastmod>` date — update it manually when making significant content changes
- The blog section exists in the HTML but contains no actual posts — it is a placeholder
- Avoid adding external JS dependencies; the site's simplicity is intentional
