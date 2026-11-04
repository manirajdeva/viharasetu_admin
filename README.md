# Viharasetu admin portal

Live at **https://admin.viharasetu.co.in** (GitHub Pages, custom domain in `CNAME`).
This repo is now the single home of the admin code. The main website lives in
[viharasetu_website](https://github.com/manirajdeva/viharasetu_website) and only keeps redirect stubs.

- **Backend:** `https://viharasetu-api.onrender.com/exec` (Express + TiDB). The URL is `PRODUCTION_SCRIPT_URL`
  in `js/api.js`. The API only answers browsers whose origin is in the Render env var `CORS_ORIGINS`
  (it includes `https://admin.viharasetu.co.in`).
- **Images** are in `images/` (copied from the main site; only the ones the admin pages use).

## Change something
1. Edit the files here.
2. Test locally: run `node mock-server/server.js` in the website repo (mock API on :3001), then serve this folder,
   e.g. `python -m http.server 5501`, and open `http://localhost:5501/` (login `admin` / `admin123`).
   On localhost the portal uses the mock API automatically; add `?api=live` once to use the real one.
3. Commit and push `main`. Pages redeploys within a minute or two.
