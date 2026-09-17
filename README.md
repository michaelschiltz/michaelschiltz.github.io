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

## Bookshelf

The Bookshelf page (`/books/`) lists one Markdown file per book in `_books/`, grouped by the year and month in `started` (newest first). Books without `started` appear under "Next up". Example, `_books/2026-09-smith-wealth-of-nations.md`:

```yaml
---
title: "The Wealth of Nations"
author: Adam Smith
released: 1776                # optional
isbn: 9780553250102           # optional; cover fetched from Open Library
# cover: /assets/img/books/wealth.jpg   # optional local cover, overrides isbn
started: 2026-09-03           # sets the month group; omit for "Next up"
finished: 2026-09-28          # optional
status: reading               # reading, finished, paused, abandoned, queued, reread, interested
---
Optional notes (shown on the book's own page).
```

Optional extra fields: `translator`, `publisher`, `blurb` (publisher's description), `started_month_only: true` (shows "Started June 2026" instead of a day), `zotero` (item key, used to update entries on re-import). `cover` may also be a full image URL.

**From Zotero.** Zotero is the master copy for the bookshelf. Books in the Zotero collection *Bookshelf* are imported on request by Claude, one file per item:

- title, author, translator, publisher, ISBN: from the Zotero fields;
- month: tag `started: YYYY-MM`; status: tag `status: …` (`read` is written as `finished`);
- publisher's description: the Zotero *Abstract* field, shown on the book's page under "From the publisher" (stored as `blurb:` in the file);
- your own notes: a child note in Zotero whose first line is `Bookshelf`. Everything below that line becomes the text of the book's page (bold, italics, links, lists and paragraphs carry over). Other notes are never published;
- cover: linked from the book's Amazon page.

Because each import rewrites the file from Zotero, edit notes and descriptions in Zotero, not in the `.md` file.

Books with no cover available get a plain title card. The layouts `_layouts/book-shelf.liquid`, `_layouts/book-review.liquid` and `_includes/book_cover.liquid` override al_folio_core's versions.
