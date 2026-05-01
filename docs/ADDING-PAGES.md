# Adding a New Page

**Audience:** TPS team members adding pages to an existing brand site
**Time:** ~15 minutes (not counting content)

---

## Before You Start

You need:
- GitHub Desktop installed and the brand repo cloned to your computer
- The finished HTML file for the new page
  (produced in Step 3 of the TPS Content Pipeline)
- The page's slug — the short URL-friendly name
  - Example: for `aceseptic.com/services/lift-stations/` the slug is `lift-stations`

---

## Step 1 — Pull the Latest Version

Before adding anything, make sure your local copy is up to date.

1. Open **GitHub Desktop**
2. Select the brand repo from the left sidebar
3. Click **Fetch origin** (top bar)
4. If there are changes, click **Pull origin**

> Always pull before you add files. This prevents conflicts.

---

## Step 2 — Create the Page Folder

Each page lives in its own folder. The folder name becomes part of the URL.

1. Open the repo folder on your computer
2. Navigate to the correct location for this page type:

| Page type | Where it lives |
|-----------|---------------|
| Service page | `services/[slug]/` |
| Blog post | `blog/[slug]/` |
| About / Company | `about/[slug]/` |
| Location page | `locations/[slug]/` |
| Top-level page | `[slug]/` (in root) |

3. Create a new folder with the page's slug as the name
   - Example: `services/lift-stations/`
   - Use lowercase letters and hyphens only — no spaces, no capitals

---

## Step 3 — Add the HTML File

1. Place the HTML file inside the folder you just created
2. **Rename the file to `index.html`**
   - Every page folder must contain a file named exactly `index.html`
   - Example: `services/lift-stations/index.html`

> Naming it `index.html` is what makes the clean URL work.
> `aceseptic.com/services/lift-stations/` instead of
> `aceseptic.com/services/lift-stations/lift-stations.html`

---

## Step 4 — Add Any New Images

If the page uses new images that aren't already in the repo, add them now.

See [`docs/ADDING-IMAGES.md`](ADDING-IMAGES.md) for the full image workflow.

---

## Step 5 — Check the CSS Links

Open the new `index.html` in a text editor and confirm the CSS file paths are correct.

Because this page is inside a subfolder, the paths need `../../` to reach the root:

```html
<!-- Correct for a page in services/lift-stations/ -->
<link rel="stylesheet" href="../../assets/css/tokens.css">
<link rel="stylesheet" href="../../assets/css/components.css">
```

If the page is two folders deep (e.g. `services/lift-stations/index.html`),
use `../../`. If it's one folder deep (e.g. `blog/index.html`), use `../`.

> Ask in the TPS Claude Admin chat if you're unsure about path depth.

---

## Step 6 — Commit and Push

1. Open **GitHub Desktop**
2. You'll see the new files listed under **Changes** on the left
3. In the **Summary** field (bottom left), type the commit message:
   ```
   v1.0 - [slug] - new page added
   ```
   Example: `v1.0 - lift-stations - new page added`
4. Click **Commit to main**
5. Click **Push origin** (top bar)

---

## Step 7 — Verify the Live Page

1. Wait 1–2 minutes for GitHub Pages to rebuild
2. Visit the page URL in a browser
   - Example: `aceseptic.com/services/lift-stations/`
3. Confirm:
   - Page loads without errors
   - Navigation appears correctly
   - Images load
   - No broken links

---

## Page URL Reference

| Folder structure | Live URL |
|------------------|----------|
| `services/lift-stations/index.html` | `domain.com/services/lift-stations/` |
| `blog/my-post-title/index.html` | `domain.com/blog/my-post-title/` |
| `about/index.html` | `domain.com/about/` |
| `index.html` (root) | `domain.com/` |

---

## Something Went Wrong?

**Page shows a 404:** The folder or file is misnamed. Check that the file is
named exactly `index.html` and the folder slug matches the URL you expect.

**Styles are broken:** The CSS file paths are wrong. See Step 5.

**Images don't load:** The image file paths are wrong or the images weren't pushed.
Open GitHub Desktop and check that image files appear in the last commit.

**Not sure:** Paste the error or screenshot into the brand's Claude Project chat.
