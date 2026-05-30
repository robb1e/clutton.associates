# clutton.associates

Website for **Clutton Associates Ltd** — the independent consulting business of
Robbie Clutton, offering fractional engineering leadership, project work and
coaching for technology organisations in transition and transformation.

A [Jekyll](https://jekyllrb.com) static site deployed to GitHub Pages.

## Running locally

```sh
bin/dev          # start the live-reloading dev server
bin/dev build    # build the static site into _site/
```

Then open <http://localhost:4000>. The script finds a suitable Ruby
(the macOS system Ruby is too old for modern Jekyll), installs gem
dependencies on first run, and starts Jekyll.

<details>
<summary>Running the steps manually</summary>

```sh
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"   # need Ruby >= 3.0
bundle install
bundle exec jekyll serve --livereload            # or: jekyll build
```
</details>

## Deployment

Pushes to `main` are built and deployed to GitHub Pages automatically via
`.github/workflows/jekyll-gh-pages.yml`. The site serves from the custom
domain `clutton.associates` — for that to resolve, the domain's DNS must point
at GitHub Pages and the domain must be set in the repository's Pages settings.

## Notes

- `offerings.md` is the source brief used to write the site. It is **not**
  published — it's listed under `exclude:` in `_config.yml`.
- See `CLAUDE.md` for structure and conventions.
