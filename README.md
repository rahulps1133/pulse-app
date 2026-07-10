# Pulse

Animated schedule viewer. Static, single-page app — no backend, no API keys, nothing to configure. Everything (CSV parsing, the 2D timeline, the 3D view) runs in the visitor's browser.

## Deploy it as a real shareable link (same flow as Hawkeye)

1. Create a new GitHub repo (e.g. `pulse-app`) and add this `index.html` to it.
2. Go to https://vercel.com, sign in, click **Add New → Project**, import that GitHub repo.
3. Framework preset: **Other**. No build command, no output directory needed — Vercel will serve `index.html` as-is.
4. Click **Deploy**. You'll get a live URL like `pulse-app.vercel.app` — that's the link you share with anyone.

Any time you want to update it: edit `index.html`, commit, push to GitHub — Vercel redeploys automatically.

## Why this one has no `api/` folder

Hawkeye needed a backend because every review call had to hit the Claude API with a secret key, and you wanted a visit counter stored server-side (Upstash). Pulse doesn't call any AI or store anything — it just reads a CSV in-browser and draws it — so there's nothing that needs a server. If later you want saved/shared projects or a usage counter, that's when an `api/` folder and a small key-value store (Upstash, same as Hawkeye) would come back into the picture.
