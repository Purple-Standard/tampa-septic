# Repo Starter — Setup Guide

**Version 1.0 — TPS Template**

This folder is the starter template for all TPS client websites.
Drop it into a new GitHub repo, fill in the [TODO] values, and commit.

---

## Step 1 — Fill In tokens.css

Open `assets/css/tokens.css` and replace every `[TODO]` value with the
correct brand color, font name, or RGB channel for this client.

This is the **only file** that needs to change to re-skin the site.
Do not add color values anywhere else.

---

## Step 2 — Replace Placeholder Images

All placeholder files in `assets/images/` are `.svg` files showing
the required dimensions. Replace them with production-ready `.webp`
files using the same filename (change extension from `.svg` to `.webp`).

**Before replacing:** confirm the image is the correct size and format.
See the Image Spec below.

---

## Step 3 — Update components.css Header

Open `assets/css/components.css` and update:
- The client name in the file header
- The version date

---

## Step 4 — Commit

Use GitHub Desktop to commit the full starter with the message:
```
v1.0 - repo initialized - [Client Name] starter template
```

---

## Image Spec

### Logos (`assets/images/logos/`)

| File | Dimensions | Format | Notes |
|---|---|---|---|
| `logo-horizontal.svg` | 480 × 120 px | SVG | Primary logo, nav + light backgrounds |
| `logo-horizontal-white.svg` | 480 × 120 px | SVG | White version, dark backgrounds / footer |
| `logo-stacked.svg` | 320 × 320 px | SVG | Centered lockup, mobile hero / social |
| `logo-icon.svg` | 96 × 96 px | SVG | Mark only, favicon source |

Logos should always be SVG. Do not use PNG or WebP for logos.

---

### Stock Images (`assets/images/stock/`)

| File | Dimensions | Format | Max Size |
|---|---|---|---|
| `stock_hero_wide.webp` | 1920 × 640 px | WebP | 300 KB |
| `stock_worker_portrait.webp` | 600 × 800 px | WebP | 150 KB |
| `stock_worker_landscape.webp` | 1200 × 600 px | WebP | 200 KB |
| `stock_worker_hero.webp` | 1200 × 700 px | WebP | 200 KB |
| `stock_team_group.webp` | 1200 × 600 px | WebP | 200 KB |
| `stock_building_office_landscape.webp` | 1200 × 600 px | WebP | 200 KB |
| `stock_building_exterior.webp` | 900 × 600 px | WebP | 150 KB |
| `stock_panel_closeup.webp` | 800 × 600 px | WebP | 150 KB |
| `stock_job_site_wide.webp` | 1200 × 600 px | WebP | 200 KB |
| `stock_job_site_detail.webp` | 800 × 600 px | WebP | 150 KB |

---

### Client Photos (`assets/images/client/`)

Images provided by the on-site photographer. See `client/README.md`
for naming conventions.

---

## CSS Editing — For Team Members

`tokens.css` is the only file you should edit for brand customization.

If a component needs a new style that doesn't exist yet, add it to
`components.css` following the existing pattern. Never use inline
styles in HTML files.

Commit CSS changes with:
```
v[X.X] - tokens.css - [what changed]
v[X.X] - components.css - [what changed]
```
