# Carmen Real — Academic website

This repository contains a Jekyll-based academic website (pages, publications, profile, and assets). Base on the template available [here](https://github.com/sbryngelson/academic-website-template).

## Quick start (local)

Prerequisites:
- Ruby (recommended 3.0+)
- Bundler (`gem install bundler`)
- Node.js/npm (optional — only for some JS tooling)

Install dependencies and run locally:

```powershell
gem install bundler
bundle install
bundle exec jekyll serve --livereload
```

The site will be available at `http://localhost:4000` by default.

To produce a production build:

```powershell
bundle exec jekyll build
```

## Notes & troubleshooting
- If you change SCSS, Jekyll rebuilds when running `jekyll serve` with `--livereload`.

