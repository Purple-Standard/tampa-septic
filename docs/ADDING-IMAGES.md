# Adding Images

**Audience:** TPS team members adding photos to a brand site
**Time:** ~10 minutes per batch

---

## Two Types of Images

| Type | What it is | Where it lives |
|------|-----------|----------------|
| **Stock** | Licensed photos purchased for the site | `assets/images/stock/` |
| **Client** | Photos taken on-site or provided by the brand | `assets/images/client/` |

Logos are managed separately and should only be updated during initial brand setup.

---

## Image Format Rules

All images on TPS sites must be **WebP format** unless noted otherwise.

| Format | Used for |
|--------|----------|
| `.webp` | All stock and client photos |
| `.svg` | Logos only — never photos |
| `.jpg` / `.png` | Not used — convert to WebP first |

> WebP files are significantly smaller than JPG or PNG, which keeps the site fast.
> If you receive a JPG or PNG, convert it before adding it to the repo.

**How to convert to WebP (free options):**
- **Squoosh** — squoosh.app (browser-based, no install needed)
- **CloudConvert** — cloudconvert.com

---

## Size and Quality Guidelines

### Stock Images

These are the approved stock image slots. Only replace an existing file if you have
a better image for that purpose. Do not add new stock slots without updating the HTML.

| Filename | Dimensions | Max File Size | Used for |
|----------|------------|---------------|----------|
| `stock_hero_wide.webp` | 1920 × 640 px | 300 KB | Homepage hero background |
| `stock_worker_portrait.webp` | 600 × 800 px | 150 KB | Vertical worker photo |
| `stock_worker_landscape.webp` | 1200 × 600 px | 200 KB | Horizontal worker photo |
| `stock_worker_hero.webp` | 1200 × 700 px | 200 KB | Worker feature image |
| `stock_team_group.webp` | 1200 × 600 px | 200 KB | Team group photo |
| `stock_building_office_landscape.webp` | 1200 × 600 px | 200 KB | Office exterior |
| `stock_building_exterior.webp` | 900 × 600 px | 150 KB | Building exterior |
| `stock_panel_closeup.webp` | 800 × 600 px | 150 KB | Equipment or detail closeup |
| `stock_job_site_wide.webp` | 1200 × 600 px | 200 KB | Wide job site shot |
| `stock_job_site_detail.webp` | 800 × 600 px | 150 KB | Job site detail |

### Client Photos

Client photos don't have fixed filenames because they vary by project.
Follow the naming convention below and aim for under **500 KB per file**.

---

## Naming Convention — Client Photos

Use this format: `client_[descriptor].webp`

The descriptor should be short, lowercase, and use hyphens (no spaces).

**Examples:**
```
client_team-portrait-john.webp
client_facility-exterior.webp
client_job-hvac-building.webp
client_truck-fleet.webp
client_owner-headshot.webp
```

**Avoid:**
- Spaces in filenames (`client team photo.webp` ✗)
- Capital letters (`Client_Team_Photo.webp` ✗)
- Generic names that don't describe the image (`IMG_4823.webp` ✗)
- Special characters (`client_job@site.webp` ✗)

---

## Step-by-Step: Adding Images

### Step 1 — Prepare the Image

1. Confirm the image is in `.webp` format
   - If not, convert it at squoosh.app before continuing
2. Confirm the file size is within the limit for its type
   - Compress in Squoosh if needed (set quality to 80–85)
3. Name the file following the convention above

### Step 2 — Place the File

1. Open the repo folder on your computer
2. Copy the image file to the correct subfolder:
   - Stock image → `assets/images/stock/`
   - Client photo → `assets/images/client/`
3. If replacing an existing stock image, delete the old `.svg` placeholder first

### Step 3 — Reference the Image in HTML

If the image is new (not replacing an existing placeholder), the HTML page
must be updated to reference it.

In the page's `index.html`, add an `<img>` tag where the image should appear:

```html
<img
  src="../../assets/images/client/client_team-portrait-john.webp"
  alt="John, lead technician at [Brand Name]"
  width="600"
  height="800"
  loading="lazy"
>
```

**Rules:**
- Always include `alt` text describing what the image shows
- Always include `width` and `height` matching the actual file dimensions
- Use `loading="lazy"` for images below the fold (not the hero)
- Use `loading="eager"` for the hero image only

> Path depth: if the HTML file is in `services/lift-stations/`, use `../../assets/...`
> If it's in the root folder, use `assets/...`

### Step 4 — Commit and Push

1. Open **GitHub Desktop**
2. Confirm the image file(s) appear under **Changes**
3. Write a commit message:
   ```
   v[X.X] - assets - added [description of images]
   ```
   Example: `v1.4 - assets - added client team photos`
4. Click **Commit to main**
5. Click **Push origin**

### Step 5 — Verify

1. Wait 1–2 minutes for GitHub Pages to rebuild
2. Visit the page in a browser
3. Confirm the image loads correctly and at the right size

---

## Something Went Wrong?

**Image shows as broken:** The file path in the HTML doesn't match the actual
file location or filename. Double-check spelling and folder depth.

**Image loads but looks blurry or stretched:** The `width` and `height` values
in the HTML don't match the actual image dimensions. Update them to match.

**File is too large:** Compress it in Squoosh at quality 80 before re-uploading.

**Not sure:** Drop the question in the brand's Claude Project chat with a screenshot.
