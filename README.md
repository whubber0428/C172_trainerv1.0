# C172 Trainer as a PWA (installable web app)

This folder is the Checklist and Procedure Trainer as a Progressive Web App. Once it's hosted on an HTTPS website, anyone can add it to their home screen. It then opens full-screen like an app, works offline, and keeps each person's progress on their own phone.

## Files
| File | What it does |
|---|---|
| `index.html` | The whole trainer |
| `manifest.webmanifest` | App name, icon, and full-screen setting |
| `sw.js` | Service worker: saves the app for offline use |
| `icons/` | Home-screen and app icons |

## Host it (free): GitHub Pages
1. Sign in at github.com and create a new **public** repository, for example `c172-trainer`.
2. Click **Add file → Upload files**, drag in **everything in this folder** (keep the `icons` folder), and click **Commit changes**.
3. Go to **Settings → Pages**. Under *Branch*, choose `main` and `/ (root)`, then click **Save**.
4. After a minute your app is live at `https://YOUR-USERNAME.github.io/c172-trainer/`.

Any static host with HTTPS also works: Netlify, Cloudflare Pages, Vercel, or your flight school's website. Upload the folder's contents as-is.

## Install it on an iPhone
1. Open the link in **Safari**.
2. Tap the **Share** button, then **Add to Home Screen**, then **Add**.
3. Open **C172 Trainer** from the home screen. It runs full-screen, and works in airplane mode after the first launch.

On Android, open the link in Chrome and tap **Install app** (or ⋮ → *Add to Home screen*).

## Updating the content
1. Replace `index.html` with the new version.
2. In `sw.js`, change `VERSION` (for example `c172-trainer-v1` → `c172-trainer-v2`).
3. Upload both files again. Phones pick up the update the next time the app opens while online.

## Good to know
- Progress is stored separately on each device and in each browser. The home-screen app and a Safari tab on the same phone keep separate progress.
- If the app goes unused for a long time, iOS can clear its saved data when the phone runs low on storage.
