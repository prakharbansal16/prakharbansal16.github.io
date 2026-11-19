# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal academic website for Prakhar Bansal (Physics PhD, University of Michigan), built on the **Hyperspace** template by HTML5 UP. It is deployed via GitHub Pages at `pb16.github.io`. There is no build step — files are served as-is.

To preview locally, open `index.html` directly in a browser or use any static file server:
```
python3 -m http.server 8000
```

## Structure

- `index.html` — single-page site with anchor-linked sections: `#intro`, `#one` (About Me), `#news` (Recent Updates), `#two` (Research tiles), `#four` (CV & Publications, incl. Selected Publications list), `#five` (Talks), `#three` (Contact)
- `research/` — one sub-page per research tile (`cosmological-tensions`, `full-shape`, `bao`, `modified-gravity`, `cmb-compression`, `21cm`)
- `talks.html` — full talk list (the homepage shows only the most recent few)
- `presentations/` — PDF slides linked from the Talks section
- `images/` — photos and figures used across the site
- `CV_Prakhar.pdf` — CV linked from the CV & Publications section
- `assets/css/main.css` — primary stylesheet; custom styles for this site are appended after the Hyperspace base styles (starting around line 4040)
- `assets/css/noscript.css`, `assets/js/` — Hyperspace template JS (jQuery, Scrollex, browser detection, etc.); do not modify these. One deliberate exception: the Scrolly offset in `assets/js/main.js` uses the nav-bar height at all widths >736px, because the Hyperspace left sidebar is replaced by a top nav bar at every width (see the "Large screens" block at the end of `main.css`)

## Key Conventions

**CSS**: Custom styles (`.intro-container`, `.research-tile`, `.talk-list`, `.resource-buttons`, etc.) live at the bottom of `assets/css/main.css`. The Hyperspace base styles occupy the bulk of the file; append new styles rather than modifying the base.

**Research sub-pages** (`research/*.html`): use `../` for all asset paths (CSS, JS, images) and link back via `../index.html`. Papers are shown with `.paper-cite` blocks; when adding a paper, also add it to the Selected Publications list in `index.html#four` and to Recent Updates (`#news`).

**Line endings**: `index.html` uses CRLF; the other HTML files use LF. Preserve whichever a file already has.

**Images**: keep photos real JPEG/PNG/WebP (iPhone HEIC files renamed to `.jpg` don't render in Chrome/Firefox), resize to ≤1400px, and strip EXIF/GPS metadata before committing.

**Contact form**: submits via Formspree (`https://formspree.io/f/xnjebrjn`).

**MathJax**: Loaded via CDN on `index.html` and `cosmological-tensions.html` for LaTeX rendering in research descriptions. Add the same `<script>` block to any new research pages that contain math.
