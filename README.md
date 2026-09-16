# michaelschiltz.github.io

Personal academic site of Michael Schiltz, built on [al-folio](https://github.com/alshedivat/al-folio) v1.x (MIT).

* Bio and news: `_pages/about.md`, `_news/`
* Publications: `_bibliography/papers.bib` (entries with `selected = {true}` appear on the front page)
* Projects: `_projects/` · CV data: `_data/cv.yml` · Social links: `_data/socials.yml`
* Data & code, teaching, talks: `_pages/`

Deploys through GitHub Actions (`.github/workflows/deploy.yml`) to the `gh-pages` branch.
Settings → Actions → General → Workflow permissions: *Read and write*; Settings → Pages: branch `gh-pages`.

## Previewing in a throwaway repo first

1. Create a new public repo, e.g. `alfolio-test`, and push this folder to its `main` branch.
2. In `_config.yml`, set `baseurl: /alfolio-test` (leave `url` as is).
3. Settings → Actions → General → Workflow permissions → *Read and write permissions*.
4. Wait for the *Deploy site* action to finish, then Settings → Pages → Source: branch `gh-pages`, folder `/ (root)`.
5. Visit `https://michaelschiltz.github.io/alfolio-test/`.

To go live, push to `michaelschiltz.github.io` with `baseurl: ""` and repeat steps 3–4.

## Accent colour

Oxblood #7B2226 (light mode) and gilt #C9A45C (dark mode) is set in a block at the end of `assets/css/main.scss`. That file is a local copy of the al_folio_core gem's stylesheet: after upgrading the gem, re-copy the gem's version and re-append the block.

## Licence

- **Site code** (the al-folio template and configuration): MIT — see `LICENSE`.
- **Content** (texts, bibliographic data, CV, the gold-standard interactive): CC0 1.0 Universal — see `LICENSE-CONTENT`. Photographs in `assets/img/` are excluded and remain © Michael Schiltz.
