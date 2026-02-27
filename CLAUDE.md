# CLAUDE.md

## Project Overview

Static HTML/CSS site for pogsummers.com — Colin Summers' painting portfolio. Hosted on GitHub Pages. No JavaScript, no build system.

## Development

No build step. Preview locally: `python3 -m http.server`

## Architecture

- **style.css** — Single site-wide stylesheet (dark theme, CSS grid galleries, CSS-only lightbox)
- **index.html** — Home/welcome page with hero image
- **departures.html** — Gallery: 11x14 departure series (21 pieces)
- **pieces.html** — Gallery: main 12x12 collection (40 pieces)
- **larger.html** — Gallery: 16x16, 18x18, 20x20 pieces (10 pieces)
- **pawlet-box.html** — Gallery: Pawlet Box series (50 pieces)
- **sold.html** — Gallery: sold pieces (27 pieces)
- **about.html** — Artist bio
- **CNAME** — GitHub Pages custom domain (pogsummers.com)

## Media Files

All images live in `media/`. Three size tiers per image:

| Role | Suffix | Width | Used in |
|------|--------|-------|---------|
| Thumbnail | `_2xx` / `_300` | ~230-300px | Gallery grid |
| Lightbox | `_med` | 640px | Click-to-enlarge view |

**Pawlet Box** uses a different naming convention:
- Thumbnails: `pawletNN_thumbnail.png`
- Lightbox: `pawletNN_large.jpeg`

The numeric thumbnail suffix varies by image (e.g., `_298`, `_231`) because widths differ with aspect ratio. If replacing with larger files in the future, update both the thumbnail and `_med` versions, and adjust the lightbox CSS max-width if the `_med` size changes.

## Deployment

GitHub Pages — push to main, no build step.
