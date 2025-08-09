## Local Development and Preview

You can preview this Jekyll site locally using either a Ruby environment or Docker.

### Option A: Docker (recommended, zero setup)

Requires Docker installed.

```bash
docker run --rm -it \
  -p 4000:4000 \
  -v "$PWD":/srv/jekyll \
  jekyll/jekyll \
  jekyll serve --watch --livereload --host 0.0.0.0
```

Then open `http://localhost:4000`.

### Option B: Ruby/Jekyll locally

1. Install Ruby (2.7+), RubyGems, and Bundler
2. Install Jekyll: `gem install jekyll bundler`
3. Serve the site:

```bash
jekyll serve --livereload
```

Notes:

- If you encounter missing theme or plugin errors, consider using the Docker method above, or create a `Gemfile` pinned to `github-pages` to mirror GitHub Pages’ dependency set.
- The site uses the `jekyll-theme-cayman` theme via `_config.yml`.