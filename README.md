# farmhub-ai-site — AnImus Enterprises marketing site

Static site for **AnImus Enterprises** (FarmHub LLC). Hand-authored HTML + one shared
`style.css`. Served by **GitHub Pages**; intended live URL **https://ai.wafarmhub.com**
(set in `CNAME`). The Squarespace site at `wafarmhub.com` is separate and untouched.

## Pages
| File | Purpose |
|------|---------|
| `index.html` | Home — hero, services (Security featured first), use cases, pricing, about, contact |
| `security.html` | **Penetration testing** — the #1 revenue offering (scoped web+API pentest) |
| `ai-lab.html` | On-prem AI Engineering Lab |
| `consulting.html` | Embedded AI consulting |
| `farmhub-iot.html` | FarmHub IoT |
| `blog.html` + `posts/` | Blog |
| `style.css` | Shared dark navy/cyan theme |
| `CNAME` | Custom domain → `ai.wafarmhub.com` |

## How to maintain it (AI- or human-editable)
1. Edit the relevant `*.html` (content lives inline; all pages share `style.css` and the same nav/footer markup).
2. Preview locally — no build step:
   ```
   python3 -m http.server 8899   # then open http://localhost:8899
   ```
3. Commit + push to `main`. GitHub Pages redeploys automatically (~1 min).

**Safety rule (public repo):** only marketing content goes here. Never commit deal
figures, client names, contracts, secrets, or anything from the private `FarmHub` repo
— git history persists even after deletion.

## Go-live checklist (one-time, operator)
1. **GitHub → repo Settings → General → change visibility → Public.**
   (GitHub Pages is free only on public repos. This repo holds only marketing copy.
   Making it public does NOT affect any other repo — visibility is per-repo.)
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch →
   Branch: `main` / `/ (root)` → Save.**
3. Wait ~1 min, confirm it serves at `https://mrham89.github.io/farmhub-ai-site/`.
4. **DNS (where wafarmhub.com is managed):** add a record
   `CNAME  ai  →  mrham89.github.io`.
5. Back in **Settings → Pages → Custom domain**, GitHub reads the `CNAME` file
   (`ai.wafarmhub.com`); check **Enforce HTTPS** once the cert provisions.
6. Confirm `https://ai.wafarmhub.com` loads with a valid certificate.
