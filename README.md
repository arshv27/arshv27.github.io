# arshv27.github.io

Personal website of Arsh Verma, served at <https://arshv27.github.io>.

Built with [al-folio](https://github.com/alshedivat/al-folio) (v1.x), a Jekyll starter whose layouts,
styles, and scripts live in the `al_folio_*` gems listed in the `Gemfile`. This repo holds only content
and configuration.

## Where things live

| Path | What it is |
| --- | --- |
| `_pages/about.md` | Home page: subtitle, bio, and the switches for news, selected papers, and social icons |
| `_news/*.md` | One file per news item (`inline: true`); the home page shows the newest five |
| `_bibliography/papers.bib` | All publications; `selected = {true}` puts a paper on the home page |
| `_pages/publications.md` | Publications page (rendered from the `.bib` file by jekyll-scholar) |
| `_pages/cv.md` | CV page with the embedded PDF |
| `assets/pdf/ArshVerma_2026.pdf` | The CV PDF |
| `assets/img/arsh_photo.jpeg` | Profile photo |
| `_data/socials.yml` | Social icons at the bottom of the home page |
| `_data/venues.yml`, `_data/coauthors.yml` | Links for venue badges and co-author names |
| `_config.yml` | Site settings; most al-folio features are switched off here |
| `resume/index.html` | Redirect to `/cv/` (kept for old links) |
| `requirements.txt` | Python packages the deploy workflow installs (al-folio stock; required for its pip cache step) |

## Updating

- **Bio:** edit the body of `_pages/about.md` (Markdown).
- **News:** add a file to `_news/` (copy an existing one and change the `date`). Only the date and body matter.
- **Papers:** add a BibTeX entry to `_bibliography/papers.bib`. Useful extra fields: `abbr` (venue badge),
  `arxiv` (ID only), `pdf`, `slides`, `video`, `code`, `website` (buttons), `selected = {true}` (home page),
  `annotation` (footnote for the author list). Files given without a full URL are looked up in `assets/pdf/`.
- **Thesis talk:** add `video = {https://www.youtube.com/watch?v=...}` to the `verma2026thesis` entry and
  fill the commented Talk link in `_news/2026-05-thesis.md`. The `slides` field there is the Google Slides
  "Publish to web" link; a PDF in `assets/pdf/` works too (give just the file name).
- **CV:** replace `assets/pdf/ArshVerma_2026.pdf` (or add a new file and update `_pages/cv.md`), and bump the
  "Last updated" line there.
- **Theme options:** `_config.yml`. See the al-folio docs at <https://github.com/alshedivat/al-folio/tree/main/docs>.

## Previewing locally

With Docker (simplest):

```sh
docker compose up
# then open http://localhost:8080
```

Or with Ruby 3.3 and ImageMagick installed:

```sh
bundle install
bundle exec jekyll serve
# then open http://localhost:4000
```

## Deploying

Pushing to `master` runs `.github/workflows/deploy.yml`, which builds the site and publishes `_site` to the
`gh-pages` branch. GitHub Pages serves that branch (Settings → Pages → Branch: `gh-pages`).
