# Deploy Bullet Forge to GitHub Pages — 5 minute setup

This is a **second, parallel deployment**. Your Cloudflare site stays exactly as-is; nothing here touches it. Run both, compare, keep whichever works better on your networks.

**Why GitHub Pages:** it's the same host (`github.io`) as the AF-VCD `pdf-bullets` tool that DHA already allows — so it has the best chance of working on the DHA laptop.

---

## Step 1 — Get a free GitHub account
Go to **https://github.com/signup**. Free account, personal email. (Free tier covers everything here.)

## Step 2 — Create a public repository
1. Click the **+** (top right) → **New repository**.
2. **Repository name:** `bullet-forge`
3. Set it to **Public** ← required for free GitHub Pages.
4. Check **Add a README file**.
5. Click **Create repository**.

## Step 3 — Upload the two files
1. In the repo, click **Add file** → **Upload files**.
2. Drag in **both** files from this folder:
   - `index.html`  ← the app
   - `.nojekyll`   ← tells GitHub to serve the file as-is (important)
3. Scroll down → **Commit changes**.

> If `.nojekyll` won't drag (Windows hides dot-files): in the repo click **Add file → Create new file**, type `.nojekyll` as the filename, leave it empty, and commit.

## Step 4 — Turn on Pages
1. Repo → **Settings** (top bar) → **Pages** (left sidebar).
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. **Branch:** `main` · **Folder:** `/ (root)` → **Save**.
4. Wait ~1 minute. The page will show your live URL.

## Step 5 — Open it
Your site will be at:

```
https://YOUR-USERNAME.github.io/bullet-forge/
```

Test it on the DHA laptop. Bookmark it.

---

## What to expect on the DHA network
- **The app should load and function** if `github.io` is in an allowed category (it's the same host as the already-authorized `pdf-bullets` tool).
- **The thesaurus may not return synonyms.** That one feature calls an outside API (`api.datamuse.com`), which the filter may still block. If so, it fails quietly — **every other function still works**. Tell me if that happens and I'll build a version with it removed entirely (zero outside calls).

## Updating it later
Repo → click `index.html` → pencil icon → **Upload files** to replace it (or drag a new `index.html` in and commit). Pages redeploys automatically in about a minute. I'll keep giving you updated `index.html` files; just drop them into whichever deployment you want.

## Note on "Public"
Free Pages requires a public repo, so the source is browsable on GitHub. Worth knowing, but it changes nothing about exposure: **your Cloudflare site is already publicly reachable**, and since the app is a single HTML file, anyone could already "View Source" on it. The libraries inside are the anonymized sets we verified — **zero names, zero ID numbers**. No PHI/PII is in the file. Public source is also a *plus* for the cybersecurity review — they can read exactly what it does.
