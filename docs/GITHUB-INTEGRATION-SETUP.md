# GitHub Integration Setup — TPS Claude Admin

**Version 1.0**
**Audience:** Michael / TPS Admin
**Purpose:** One-time setup to connect the PURPLE-STANDARD GitHub org
to Claude Projects, and per-repo steps when adding a new brand.

---

## Overview

The Claude GitHub integration lets Claude read live repo files during chat sessions.
Once connected, you can paste a filename and Claude will pull the current version
directly — no download/re-upload needed.

This is a two-layer setup:
1. **Org-level** — Install the Claude GitHub App on the PURPLE-STANDARD organization (once)
2. **Project-level** — Connect each brand repo to its Claude Project (once per brand)

---

## Part 1 — Install the Claude GitHub App (One-Time)

This grants Claude access to repos in the PURPLE-STANDARD organization.

1. Go to **claude.ai** and open any Project
2. In the Project, click **Project Settings** (gear icon or top right)
3. Look for the **GitHub** section and click **Connect repository**
4. You'll be prompted to install the **Claude GitHub App**
5. Click the link to GitHub and select **PURPLE-STANDARD** as the organization
6. When asked which repos to grant access to, select:
   - **All repositories** (recommended — easier to manage as you add brands)
   - Or select specific repos if you prefer tighter control
7. Click **Install & Authorize**
8. Return to claude.ai — the connection should now be active

> You must be an admin of the PURPLE-STANDARD GitHub organization to complete this step.
> If you get a permissions error, check your org role under github.com/orgs/PURPLE-STANDARD/people

---

## Part 2 — Connect a Repo to a Claude Project (Per Brand)

Repeat these steps each time a new brand repo is created.

1. Open the brand's Claude Project (e.g. **ACE Septic & Waste**)
2. Click **Project Settings**
3. Under **GitHub**, click **Connect repository**
4. Select the brand's repo from the list (e.g. `ace-septic-waste`)
5. Click **Connect**
6. The repo is now linked — Claude can read files from it in any chat within this Project

> If the repo doesn't appear in the list, the GitHub App may not have been
> granted access to it. Go to github.com/settings/installations, find the
> Claude app, and update the repo permissions to include the new repo.

---

## Part 3 — Using the Integration in Chat

Once connected, you can reference repo files naturally in chat:

**Examples:**
- *"Pull the current index.html for ACE and update the nav to add a Lift Stations link"*
- *"Read tokens.css and confirm the accent color is correct for Purple Current"*
- *"Show me what's in services/lift-stations/index.html"*

Claude will fetch the live file from the repo, make the changes in the chat,
and return the updated file for you to copy back and commit via GitHub Desktop.

> Note: Claude reads repo files but does not push commits directly.
> All commits still happen through GitHub Desktop.

---

## Part 4 — Adding a CLAUDE.md File (Recommended)

Each brand repo can include a `CLAUDE.md` file in the root.
This file tells Claude the rules and context for that specific codebase.

Suggested contents for each brand repo's `CLAUDE.md`:

```markdown
# CLAUDE.md — [Brand Name]

## Brand
- Full name: [Brand Name]
- Domain: [domain.com]
- TPS affiliation: Powered by The Purple Standard

## CSS Rules
- tokens.css is the only file that should be edited for brand customization
- Never add color values directly to components.css or HTML files
- All brand colors and fonts are defined in tokens.css

## Commit Format
- v[X.X] - [filename] - [what changed]
- Never use "final," "revised," "updated," or "new" in a commit message

## File Naming
- Page folders: lowercase-with-hyphens
- Client images: client_[descriptor].webp
- Stock images: stock_[descriptor].webp

## Page Structure
- Every page lives in its own folder as index.html
- CSS paths use ../../ for pages in subdirectories
```

This file is read automatically by Claude Code (if you use it later)
and provides helpful context in claude.ai chats.

---

## Brand Repo Connection Checklist

| Brand | Repo Name | Claude Project | Connected? |
|-------|-----------|---------------|------------|
| ACE Septic & Waste | `ace-septic-waste` | ACE Septic & Waste | ☐ |
| Purple Current | `purple-current` | Purple Current | ☐ |
| Boyette Pump & Well | `boyette-pump-well` | Boyette Pump & Well | ☐ |
| Southern Water & Soil | `southern-water-soil` | Southern Water Distribution | ☐ |
| WTR DR | `wtr-dr` | WTR DR | ☐ |
| TPS Climate Solutions | `tps-climate-solutions` | TPS Climate Solutions | ☐ |
| Roofing (TBD) | TBD | Unnamed Roofing Company | ☐ |
| TPS Parent | `the-purple-standard` | The Purple Standard | ☐ |

---

## Troubleshooting

**Repo doesn't appear when connecting to a Project:**
Go to github.com/settings/installations → find Claude → update repo access.

**"Private repository" warning in claude.ai:**
The GitHub App doesn't have access to that repo yet. See above.

**Claude can't find a file I know exists:**
Confirm the filename and path are exact. File paths are case-sensitive on GitHub.
Use the **Sync** button in Project Settings to force a refresh.

**GitHub App needs to be re-authorized:**
Go to claude.ai Project Settings → GitHub → Reconnect.
