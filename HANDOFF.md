# Handoff — push this to GitHub + enable Pages

For **Claude Code** (or Dom) running on the local machine. You have the GitHub CLI (`gh`) installed.

> ⚠️ **The repo root is THIS folder** — `Kids\Wyatt\Mascot\mascot-camp-2026-hub\` — **not** the parent `Mascot\` folder. The parent contains private clearances and signed waivers that must never be committed. `cd` into this folder first and init the repo *here*.

---

## Step 0 — open a terminal in this folder

```bash
cd "C:/Users/domin/OneDrive/Documents/Kids/Wyatt/Mascot/mascot-camp-2026-hub"
```

## Step 1 — confirm you're in the right place

You should see `index.html`, `README.md`, `HANDOFF.md`, `.gitignore`, and `assets/`. You should **NOT** see any `*clearance*`, `*waiver*`, or `*Application*` PDFs. If you do, you're in the wrong folder — stop.

```bash
ls
```

## Step 2 — init and commit

```bash
git init -b main
git add .
git commit -m "Mascot Camp 2026 command center — Dom & Wyatt"
```

## Step 3 — create the GitHub repo and push

Pick ONE.

**Private repo (recommended for the family):**
```bash
gh repo create mascot-camp-2026-hub --private --source=. --remote=origin --push
```

**Public repo (needed if you want free GitHub Pages):**
```bash
gh repo create mascot-camp-2026-hub --public --source=. --remote=origin --push
```

## Step 4 — turn on GitHub Pages

**Note on plans:** GitHub Pages serves a **public** repo's site for free. Serving a **private** repo's site requires a paid plan (Pro/Team/Enterprise). If you're on Free and want it live on the web, use the public repo from Step 3 — the content here is safe to publish (no personal documents are committed).

Enable Pages from the `main` branch, root folder:

```bash
gh api --method POST -H "Accept: application/vnd.github+json" \
  "/repos/{owner}/mascot-camp-2026-hub/pages" \
  -f "source[branch]=main" -f "source[path]=/"
```
Replace `{owner}` with your GitHub username. (If that returns 409/already-exists, Pages is already on.)

Get the live URL once it builds (~1 min):
```bash
gh api "/repos/{owner}/mascot-camp-2026-hub/pages" --jq .html_url
```
It will be: **`https://{owner}.github.io/mascot-camp-2026-hub/`**

*Web UI fallback:* GitHub → repo → **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `/ (root)` → Save.**

## Step 5 — verify

Open the Pages URL. The mascot image, the two lunch-order PDFs, the map links, and the live countdown should all work (relative paths handle the `/mascot-camp-2026-hub/` subpath automatically).

---

## Optional — add the parking pass to the live site

The **parking map** is already bundled (`assets/documents/Parking-Map.pdf`, shown inline). The **parking pass** is not committed (it can carry a name/barcode). To add it:
1. Save `Mascot Day July 9 Parking Pass.pdf` into `assets/documents/`.
2. In `index.html`, in the **Documents** section, point the parking-pass row at the local PDF.
3. `git add . && git commit -m "Add parking pass" && git push`
4. ⚠️ Only do this if the repo is **private**.

## Updating later
```bash
git add . && git commit -m "Update itinerary" && git push
```
Pages redeploys automatically.
