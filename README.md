# Ripple Heads-Up — GitHub Pages (PWA) repository

This folder is **exactly** what goes in the GitHub repo so:

1. The app is a real **PWA** on HTTPS  
2. **PWABuilder** can package it for the **Microsoft Store**

Support: **amelie.ai.support@gmail.com**

---

## Files that must be in the repo (root of the site)

```
your-repo/
├── index.html                 ← the app (required)
├── manifest.webmanifest       ← PWA manifest (required)
├── sw.js                      ← service worker (required)
├── privacy.html               ← privacy policy page (required for Store)
├── icons/
│   ├── icon-192.png           ← required
│   ├── icon-512.png           ← required
│   ├── icon-180.png           ← Apple touch (recommended)
│   └── icon-48.png
└── README.md                  ← optional
```

**Do not** put only the HTML file. PWABuilder needs the live HTTPS URL to see the **manifest** and **service worker**.

---

## Step-by-step: GitHub

1. Create a new GitHub repository (public is simplest for GitHub Pages).
2. Upload **all** files above into the **root** of the repo (or the `docs` folder if you prefer Pages from `/docs`).
3. **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` (or `master`) → folder **/ (root)**  
     (or `/docs` if that is where you put the files)
4. Save. Wait 1–2 minutes.
5. Your HTTPS URL will be:

   `https://YOUR_GITHUB_USERNAME.github.io/REPO_NAME/`

   Example: `https://amelie-ai.github.io/ripple-heads-up/`

6. Open that URL in Edge or Chrome. Confirm the app loads.
7. Open `https://YOUR_URL/privacy.html` — that is your **Privacy policy URL** for the Store.

---

## Privacy policy URLs (copy these into Partner Center)

| Place | URL |
|--------|-----|
| **Microsoft Store** → Privacy policy URL | `https://YOUR_GITHUB_USERNAME.github.io/REPO_NAME/privacy.html` |
| **Website** (optional) | `https://YOUR_GITHUB_USERNAME.github.io/REPO_NAME/` |
| **Support email** | amelie.ai.support@gmail.com |

---

## PWABuilder → Microsoft Store

1. Go to [https://www.pwabuilder.com](https://www.pwabuilder.com)
2. Paste your **GitHub Pages HTTPS URL** (the site root, not privacy.html) → **Start**
3. Fix any red items if shown (manifest / service worker should already pass)
4. **Package for Stores** → **Windows** → **Generate**
5. Enter Partner Center **Package ID**, **Publisher ID**, **Publisher display name**
6. Download the zip → upload **`.msixbundle`** and **`.classic.appxbundle`** to Partner Center  
   (do **not** upload the sideload package)

Full Partner Center sequence: see `MS_STORE_PROCEDURE.md` in the complete package.

---

## After you update the app

1. Replace `index.html` with the new Rev file (still named `index.html`)
2. Bump the cache name in `sw.js` (e.g. `rhu-v0-1-20`) so users get the new version
3. Commit and push — GitHub Pages updates automatically
