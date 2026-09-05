# Salary Ledger — turning it into a real Android app

This folder is a complete installable web app (PWA). To get it onto your
phone as an actual app icon (not just a browser tab), it needs to be hosted
online first — a service worker and "Install app" prompt only work over
https, not from a file opened directly on your phone.

## Step 1 — Host it for free (GitHub Pages)

1. Go to https://github.com and create a free account if you don't have one.
2. Click "New repository", name it something like `salary-ledger`, set it
   to Public, and create it.
3. On the repository page, click "Add file" → "Upload files", then drag in
   every file from this folder (index.html, manifest.json, service-worker.js,
   icon-192.png, icon-512.png, icon-512-maskable.png). Commit the changes.
4. Go to the repo's Settings → Pages. Under "Source", choose the `main`
   branch and save.
5. After a minute, GitHub gives you a live URL like:
   `https://yourusername.github.io/salary-ledger/`

## Step 2 — Install it on your phone

1. Open that URL in Chrome on your Android phone.
2. Chrome will show an "Install app" banner (or tap the ⋮ menu → "Install app"
   / "Add to Home screen").
3. It installs like a normal app — its own icon, opens full-screen with no
   browser bar, and keeps working offline since the service worker caches it.

This is already a real app at this point. Most people stop here.

## Step 3 (optional) — Get an actual .apk file

If you specifically want an installable .apk (e.g. to share the file
directly or list it on the Play Store):

1. Go to https://www.pwabuilder.com
2. Paste your GitHub Pages URL from Step 1 and click "Start".
3. PWABuilder scores your app (it should pass, since manifest + service
   worker + icons are already set up) and lets you download an Android
   package under the "Android" tab.
4. It gives you a signed .apk / .aab you can sideload onto your phone or
   submit to the Google Play Store.

## Notes

- Your salary and spending data is stored per-device through the app's
  storage — it stays on whichever device/browser you use it from.
- If you edit index.html later, just re-upload the changed file to the
  same GitHub repo — Pages updates automatically.
