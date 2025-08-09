## Site Configuration (`_config.yml`)

The site is configured via Jekyll’s `_config.yml`. These options are the public "API" for customizing behavior and content.

Current keys and their purpose:

- `title` (string): Site title.
- `description` (string): Short tagline used in meta and headers.
- `show_downloads` (boolean): Toggles the extra call-to-action button in the header.
- `twitter_username` (string): Used by themes/SEO for social metadata.
- `github_username` (string): Used by themes/SEO for social metadata.
- `youtube` (string): YouTube handle/slug for metadata.
- `post_search` (boolean): Optional flag for search features (theme-dependent).
- `google_analytics` (string): Google Analytics Measurement ID. When set, the layout injects gtag.
- `theme` (string): Jekyll theme. Currently `jekyll-theme-cayman`.
- `jekyll_admin.hidden_links` (array of strings): Hides sections in Jekyll Admin if used.

### Example: Enable Google Analytics

```yaml
# _config.yml
google_analytics: G-XXXXXXXXXX
```

The default layout detects this and injects the gtag script automatically.

### Example: Toggle Header Button

```yaml
# _config.yml
show_downloads: true  # shows the "Submit Your Docker Extensions Ideas" button
# show_downloads: false # hides it
```

### Changing the Theme

The site uses `jekyll-theme-cayman`. To switch, set:

```yaml
# _config.yml
theme: jekyll-theme-cayman
```

Note: If you serve locally outside GitHub Pages, ensure the theme gem is installed or use the GitHub Pages Docker image (see Local Development).