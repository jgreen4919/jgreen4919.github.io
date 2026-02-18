# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

Personal academic website for Jon Green (Duke University, Political Science). Built with Jekyll using the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template, which is based on the Minimal Mistakes theme. Hosted on GitHub Pages at https://jgreen4919.github.io.

## Local Development

```bash
bundle install              # install Ruby dependencies (delete Gemfile.lock on errors)
jekyll serve -l -H localhost  # serve at localhost:4000 with live reload
```

Note: `_config.yml` changes require restarting the server.

## Build JS Assets

```bash
npm run build:js   # uglify/concat JS into assets/js/main.min.js
```

## Site Architecture

### Content Collections (`_config.yml` defines these)

| Collection       | Directory        | Active nav? | Notes                              |
|-----------------|------------------|-------------|------------------------------------|
| Publications    | `_publications/` | Yes         | Markdown per paper, sorted reversed|
| Teaching        | `_teaching/`     | Yes         | Numbered filenames for ordering    |
| Posts (Notes)   | `_posts/`        | Yes         | Blog-style notes page              |
| Talks           | `_talks/`        | No (commented out) | Template leftovers           |
| Portfolio       | `_portfolio/`    | No (commented out) | Template leftovers           |

### Key Directories

- `_pages/` — Top-level site pages (about, cv, publications, teaching, notes, etc.)
- `_layouts/` — HTML layout templates (single, archive, talk, splash, etc.)
- `_includes/` — Reusable HTML partials (author-profile, archive-single, head, footer, etc.)
- `_sass/` — SCSS stylesheets
- `_data/navigation.yml` — Main navigation menu configuration
- `files/` — Static files (PDFs like CV, papers). Served at `/files/filename.pdf`
- `images/` — Site images including author avatar
- `_site/` — Generated output (gitignored in spirit, don't edit directly)

### How Pages Work

- `_pages/about.md` — Homepage (permalink: `/`), contains author bio
- `_pages/publications.md` — Lists all `_publications/` entries in reverse order
- `_pages/teaching.html` — Lists all `_teaching/` entries
- `_pages/cv.md` — Links to the PDF CV in `files/`
- `_pages/notes.md` — Blog/notes archive

### Adding Content

**New publication:** Create `_publications/YYYY-short-title.md` with front matter including `title`, `collection`, `permalink`, `date`, `venue`, etc. Follow existing files as templates.

**New teaching entry:** Create `_teaching/NN-course-name.md` with numeric prefix for ordering.

**New note/post:** Create `_posts/YYYY-MM-DD-title.md`.

### Configuration

- `_config.yml` — Site-wide settings: author info, social links, collection definitions, plugin config
- `_data/navigation.yml` — Controls which pages appear in the top nav bar
- `_data/authors.yml` — Author metadata
