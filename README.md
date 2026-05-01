# TPS Website Starter Template

**Version 1.0 — The Purple Standard**

This is the master template for all TPS brand websites. Every brand repo starts here.
Do not build pages directly in this repo — clone it first.

---

## What's in This Repo

```
tps-starter-template/
├── assets/
│   ├── css/
│   │   ├── tokens.css          ← Brand colors, fonts, spacing (edit this per brand)
│   │   └── components.css      ← Shared layout and UI styles (do not edit)
│   └── images/
│       ├── logos/              ← Brand logo files (SVG)
│       ├── stock/              ← Licensed stock photography (WebP)
│       └── client/             ← Client-provided photos (WebP)
├── docs/
│   ├── SETUP-NEW-BRAND.md      ← Start here when cloning for a new brand
│   ├── ADDING-PAGES.md         ← How to add a new page to an existing brand site
│   └── ADDING-IMAGES.md        ← How to add stock or client photos
├── index.html                  ← Base homepage template
├── SETUP.md                    ← CSS and image setup reference
├── .gitignore                  ← Prevents junk files from being committed
└── LICENSE                     ← Proprietary — all rights reserved
```

---

## Starting a New Brand Site

See [`docs/SETUP-NEW-BRAND.md`](docs/SETUP-NEW-BRAND.md) for the full checklist.

The short version:
1. Clone this repo into a new repo named for the brand (e.g. `ace-septic-waste`)
2. Fill in `assets/css/tokens.css` with brand colors and fonts
3. Replace placeholder images in `assets/images/`
4. Update `index.html` with brand name and nav links
5. Enable GitHub Pages in repo settings
6. Connect the repo to the brand's Claude Project

---

## Adding Pages or Images to an Existing Site

- Adding a page → [`docs/ADDING-PAGES.md`](docs/ADDING-PAGES.md)
- Adding images → [`docs/ADDING-IMAGES.md`](docs/ADDING-IMAGES.md)

---

## CSS Rules

`tokens.css` is the **only** file that should be edited for brand customization.
Never add color values directly to `components.css` or any HTML file.

---

## Ownership

Copyright © 2026 The Purple Standard. All rights reserved.
See [`LICENSE`](LICENSE) for details.
