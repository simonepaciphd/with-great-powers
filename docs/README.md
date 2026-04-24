# Project landing page

Jekyll-powered landing page for *With Great Powers: A Practical Guide to Agentic AI for Social Science Research*.

## Files

- `_config.yml` — Jekyll config; uses the built-in `jekyll-theme-cayman`.
- `index.md` — single-page site content.
- `assets/css/style.scss` — custom styles layered on top of Cayman.

## Publishing on GitHub Pages

In GitHub → **Settings** → **Pages**, set **Source: Deploy from a branch**, **Branch: main**, **Folder: `/docs`**. After the first build (usually a minute or two), the site will be live at `https://<username>.github.io/<repo>/`.

## Local preview

```bash
cd docs
bundle init && bundle add jekyll github-pages
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Content sources

- Paper text paraphrased from `drafts/current draft/Draft-04-23-2026.pdf` (abstract, §2, §3, §3.5).
- Figures 1–4 are recreated in HTML/CSS — not screenshotted — so they remain legible and responsive.
- Repo asset descriptions mirror the top-level `README.md`.
