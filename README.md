# Keco Studio Website

This folder has two versions of the same site, both exported from a
[Claude Design](https://claude.ai/design) project:

- **Root `.dc.html` files** — component source (nav, footer, and one file per page), assembled at runtime by `support.js`. Reference only, for quick local preview — not the deploy target.
- **`site/`** — the deployable build. Clean routes (`/pricing`, `/marketplace`, ...), SEO meta tags, `sitemap.xml`, `robots.txt`, and a `vercel.json` already configured for clean URLs. **This is what should actually be deployed** (Vercel, GitHub Pages, etc.).

Don't edit both independently — the two are currently in sync because
they came from the same export, but nothing keeps them that way
automatically. If you make changes, either re-export both from Claude
Design, or update `site/` directly since that's the one that ships.

## Local preview

Serve this folder over HTTP:

```bash
python3 -m http.server 8743
```

Then open e.g. 
```
http://localhost:8743/Keco%20Homepage.dc.html
```

## Deploying `site/`

`site/` is a static folder ready to serve as-is (e.g. drag it into
Vercel, or `vercel --cwd site`). No build step required.
