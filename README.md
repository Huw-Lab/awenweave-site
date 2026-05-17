# Awen Weave docs site

The public-facing site for **Awen Weave** — a Welsh-rooted framework
for weaving together knowledge, relationships, place, data and human
insight into coherent living systems.

Lives at: https://awenweave.com

## Editing

Content is markdown under `docs/`. Each page exists in two versions:

- `page.md` — English (default).
- `page.cy.md` — Welsh (Cymraeg).

Edit either via the GitHub web UI (every page has an "Edit this page"
link in the rendered site) or via a local clone.

The English file is the canonical structure. When you add a new page,
add both `page.md` and `page.cy.md`. Welsh translations may lag behind
English drafting; mark in-progress Welsh pages with the
`_[Welsh translation pending — tutor pass.]_` annotation.

Navigation entries in `mkdocs.yml` always point at the **English**
filename (e.g. `about/index.md`, not `about/index.cy.md`). The
`mkdocs-static-i18n` plugin auto-resolves the Welsh variant at build
time. Pointing nav at a `.cy.md` file would silently fall back to the
English file on the `cy` build — `mkdocs build --strict` doesn't
catch this.

## Building locally

```bash
pip install -r requirements.txt
mkdocs serve
# Site at http://127.0.0.1:8000
```

`mkdocs build --strict` is what CI runs; treat warnings as errors
locally too:

```bash
mkdocs build --strict
```

## Deploying

Push to `main`. GitHub Actions (`.github/workflows/deploy.yml`) builds
and deploys to GitHub Pages, which serves at https://awenweave.com via
the `docs/CNAME` file.

## License

Content: **CC-BY-SA 4.0** (see `LICENSE`).
Code samples within content: **AGPLv3** unless otherwise marked.
"Awen Weave" wordmark: trademark pending (Huw-Lab).
