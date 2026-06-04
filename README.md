# AnImus Labs — marketing site

Static marketing site for **AnImus Labs**. Hand-authored HTML + one shared `style.css`,
served by **GitHub Pages**.

**Live:** https://mrham89.github.io/farmhub-ai-site/

## Pages
| File | Purpose |
|------|---------|
| `index.html` | Home — hero, services, use cases, pricing, about, contact |
| `security.html` | Penetration testing |
| `ai-lab.html` | On-prem AI Engineering Lab |
| `consulting.html` | Embedded AI consulting |
| `farmhub-iot.html` | FarmHub IoT |
| `blog.html` + `posts/` | Blog |
| `style.css` | Shared theme |

## Edit / preview / deploy
1. Edit the relevant `*.html` (content is inline; all pages share `style.css` + the same nav/footer).
2. Preview locally (no build step): `python3 -m http.server 8899` → open `http://localhost:8899`.
3. Commit + push to `main` — GitHub Pages redeploys automatically (~1 min).

> **This repository is PUBLIC.** Commit marketing content only — never secrets, credentials,
> customer information, pricing/deal data, or any private business material. Git history
> persists even after a file is deleted.

## Custom domain (when a dedicated domain is registered)
1. Register a domain at any registrar.
2. DNS:
   - **Apex** (e.g. `example.com`): four **A** records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`; plus a **CNAME** `www → mrham89.github.io`.
   - **Subdomain** (e.g. `www`): a single **CNAME** → `mrham89.github.io`.
3. Add a `CNAME` file containing the domain, set it in **Settings → Pages → Custom domain**, then enable **Enforce HTTPS**.
