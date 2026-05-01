# Setting Up a New Brand Site

**Audience:** TPS admin / whoever is initializing a new brand repo
**Time:** ~30 minutes

---

## Before You Start

You need:
- Access to the PURPLE-STANDARD GitHub organization
- GitHub Desktop installed on your computer
- The brand's approved color values, fonts, and logo files
- The brand's domain name confirmed

---

## Step 1 — Clone the Template Repo

1. Go to **github.com/PURPLE-STANDARD/tps-starter-template**
2. Click the green **Use this template** button (top right)
3. Click **Create a new repository**
4. Set the owner to **PURPLE-STANDARD** (not your personal account)
5. Name the repo using this format: `[brand-slug]`
   - Examples: `ace-septic-waste`, `purple-current`, `boyette-pump-well`
6. Set visibility to **Private**
7. Click **Create repository**

---

## Step 2 — Clone to Your Computer

1. Open **GitHub Desktop**
2. Go to **File → Clone Repository**
3. Find the new repo under the PURPLE-STANDARD organization
4. Choose where to save it on your computer
5. Click **Clone**

---

## Step 3 — Fill In tokens.css

1. Open the repo folder on your computer
2. Navigate to `assets/css/tokens.css`
3. Open it in a text editor (Notepad, TextEdit, or VS Code)
4. Replace every `[TODO]` value with the correct brand value
5. Save the file

> `tokens.css` is the **only** CSS file you should edit.
> All brand colors, fonts, and spacing live here.
> Do not touch `components.css`.

When done, commit with this message:
```
v1.1 - tokens.css - [Brand Name] brand colors and fonts
```

---

## Step 4 — Replace Placeholder Images

The `assets/images/` folder contains placeholder `.svg` files showing the required dimensions.

**Logos** (`assets/images/logos/`)
- Replace each `.svg` placeholder with the real brand logo SVG
- Keep the same filename — just swap the file
- Logos must stay as `.svg` format

**Stock images** (`assets/images/stock/`)
- Replace each `.svg` placeholder with a production `.webp` file
- Change the extension from `.svg` to `.webp`
- Check the size and format requirements in `SETUP.md`

See [`docs/ADDING-IMAGES.md`](ADDING-IMAGES.md) for the full image workflow.

When done, commit with this message:
```
v1.2 - assets - replaced placeholder images with [Brand Name] assets
```

---

## Step 5 — Update index.html

1. Open `index.html` in a text editor
2. Replace every `[TODO]` and `[placeholder]` value:
   - Brand name
   - Page title and meta description
   - Domain URL in the canonical tag
   - Phone number
   - Email address
   - City and state
   - Nav links (add the brand's real service pages)
   - Google Fonts import (match the fonts set in tokens.css)
3. Save the file

Commit with:
```
v1.3 - index.html - [Brand Name] homepage content and nav
```

---

## Step 6 — Update components.css Header

1. Open `assets/css/components.css`
2. Update the file header at the top:
   - Client name
   - Version date (today's date)
3. Save the file

Commit with:
```
v1.1 - components.css - updated header for [Brand Name]
```

---

## Step 7 — Enable GitHub Pages

1. Go to the repo on github.com
2. Click **Settings** (top nav)
3. Click **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Set branch to **main**, folder to **/ (root)**
6. Click **Save**
7. Wait 1–2 minutes, then visit the Pages URL to confirm it loads

The URL will look like: `purple-standard.github.io/[brand-slug]/`

> This is a staging URL. The live domain is connected separately (see Step 8).

---

## Step 8 — Connect the Custom Domain

1. In repo **Settings → Pages**, enter the brand's domain under **Custom domain**
2. Follow GitHub's DNS instructions to point the domain at GitHub Pages
3. Check **Enforce HTTPS** once DNS has propagated (can take up to 24 hours)

---

## Step 9 — Connect to Claude Project

1. Open the brand's Project in claude.ai
2. Go to **Project Settings**
3. Under **GitHub**, click **Connect repository**
4. Select the new repo from the PURPLE-STANDARD organization
5. Claude will now be able to read live repo files in this Project's chats

> If the repo doesn't appear, the Claude GitHub App may need to be granted
> access to it. See the GitHub Integration Setup guide in TPS Claude Admin.

---

## Commit Version Log

| Commit | File | What Changed |
|--------|------|--------------|
| v1.0 | (all) | Repo initialized from TPS starter template |
| v1.1 | tokens.css | Brand colors and fonts |
| v1.2 | assets/ | Placeholder images replaced |
| v1.3 | index.html | Homepage content and nav |
| v1.1 | components.css | File header updated |

---

## Done

The repo is live, the domain is connected, and Claude has access.
Next step: begin Step 1 of the TPS Content Pipeline (KWR) in the brand's Claude Project.
