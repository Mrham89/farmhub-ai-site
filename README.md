# farmhub-ai-site — AnImus Enterprises marketing site

Static site for **AnImus Enterprises** (FarmHub LLC). Hand-authored HTML + one shared
`style.css`. Served by **GitHub Pages** via the "Static HTML" Actions workflow.

**Live URL:** https://mrham89.github.io/farmhub-ai-site/

**Domain:** AnImus is a separate brand arm from WA FarmHub and will get its **own
dedicated domain** (NOT a `wafarmhub.com` subdomain). Until then it serves at the
github.io URL. To attach a domain later, see "Custom domain (later)" below.

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

## Hosting (done)
- Repo is **Public**; GitHub Pages enabled via **Settings → Pages → Source: GitHub Actions → "Static HTML"** workflow (`.github/workflows/static.yml`). Auto-deploys on every push to `main`.
- Live at **https://mrham89.github.io/farmhub-ai-site/**.

## Custom domain (later — when a dedicated AnImus domain is chosen)
1. Register an AnImus domain (~$12/yr) at any registrar (Cloudflare Registrar / Porkbun / Namecheap).
2. DNS:
   - **Apex** (e.g. `animussec.com`): add 4 **A** records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`; plus a **CNAME** `www → mrham89.github.io`.
   - **Subdomain only** (e.g. `www.` or `app.`): a single **CNAME** → `mrham89.github.io`.
3. Add a `CNAME` file to this repo containing the chosen domain, AND set it in **Settings → Pages → Custom domain**.
4. Tick **Enforce HTTPS** once the cert provisions.
   - Domain front-runner: **`animuslabs.ai`** (on-brand for an AI lab); `animuslabs.io` cheaper. Avoid plain "Animus" — `animus.com` is an existing pentest firm (name collision).

## Ideas / future dev
- **"Bucket-bot" mascot** — an ORIGINAL flat-SVG robot (or chip-creature) hauling two buckets of glowing cyan "data" — the "your AI agents haul the work for you" metaphor. Use as a footer doodle / section icon / 404 art. **Must be original** (a robot, NOT a broom) — the Fantasia Sorcerer's-Apprentice broom-with-buckets is Disney-copyrighted and off-limits. Palette: navy/cyan/gold.
- **Downloadable PDF one-pager** — generate from `Businees_Dev/marketing/animus_pentest_offer.md` via the AnImus MCP `bid_export` tool (pandoc in-container); link from `security.html` as a trust artifact.
- **Sample (redacted) pentest report** download — strong credibility signal (the move animus.com uses).
