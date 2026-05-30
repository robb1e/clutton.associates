# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Project overview

Marketing website for **Clutton Associates Ltd**, the independent consulting
business of Robbie Clutton — fractional engineering leadership, project work
and coaching. Built as a Jekyll static site and deployed to GitHub Pages.

## Development

- `bin/dev` — start the live-reloading dev server at http://localhost:4000
- `bin/dev build` — build the static site into `_site/`

`bin/dev` locates a Homebrew Ruby (the macOS system Ruby 2.6 is too old for
modern Jekyll), installs gem dependencies on first run, then runs Jekyll.
To run the steps by hand, put a Ruby >= 3.0 on `PATH` first, e.g.
`export PATH="/opt/homebrew/opt/ruby/bin:$PATH"`, then use
`bundle install` / `bundle exec jekyll serve`.

## Information architecture

- `/` — home (`index.html`): hero, positioning, engagement types, focus areas
- `/services/` — engagement types and areas of focus (`services.html`)
- `/coaching/` — the coaching offering (`coaching.md`)
- `/about/` — Robbie's bio, career, writing (`about.md`)
- `/contact/` — ways to get in touch (`contact.md`)
- `/404.html` — not-found page

## Structure

- `_layouts/default.html` — base shell: head, header nav, footer
- `_layouts/page.html` — inherits `default`; adds a navy page-header band,
  a `.prose` container, and a closing call-to-action. Used by markdown pages.
- `index.html` and `services.html` use `default` directly and compose their
  own `<section>` blocks.
- `assets/css/main.css` — all styles (CSS custom properties at the top)
- `assets/img/favicon.svg` — the "CA" mark, also used as the nav logo

## Conventions

- Shared links (Calendly, LinkedIn, blog, email) live under `links:` in
  `_config.yml` — reference them, don't hard-code.
- Markdown pages set `title`, `eyebrow`, `tagline` front matter; the
  page-header band reads these. Set `hide_cta: true` to drop the closing CTA.
- `offerings.md` is the **source brief**, not site content. It is listed under
  `exclude:` in `_config.yml` and must never be published.
- Do not publish client names. Former employers (Snyk, VMware, Pivotal Labs,
  BT, The Guardian) are Robbie's own roles and are fine to reference.

## Deployment

Pushing to `main` triggers `.github/workflows/jekyll-gh-pages.yml`, which
builds with Jekyll and deploys to GitHub Pages. `CNAME` sets the custom
domain `clutton.associates` (DNS must point at GitHub Pages).
