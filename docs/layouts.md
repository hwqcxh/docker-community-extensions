## Layouts and Public Components

This site has a primary layout: `_layouts/default.html`. It acts as the main reusable component, exposing slots and behavior via Liquid variables.

Key features:

- Injects Google Analytics when `site.google_analytics` is set
- Loads theme stylesheet and SEO tags (`{% seo %}`)
- Renders GitHub buttons (Star, Fork, Watch, Follow)
- Shows an optional header button when `site.show_downloads` is true
- Renders page-specific content via the `{{ content }}` slot
- Includes a footer with links and widgets

### Default Layout Structure

```html
<!DOCTYPE html>
<html lang="{{ site.lang | default: "en-US" }}">
  <head>
    {% if site.google_analytics %}
      <!-- gtag injected -->
    {% endif %}
    <meta charset="UTF-8">
    <link rel="stylesheet" href="{{ '/assets/css/style.css?v=' | append: site.github.build_revision | relative_url }}">
    {% seo %}
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
  <body>
    <header class="page-header" role="banner">
      <!-- GitHub buttons and titles -->
      {% if site.github.is_project_page %}
        <a href="{{ site.github.repository_url }}" class="btn">View on GitHub</a>
      {% endif %}
      {% if site.show_downloads %}
        <a href="https://github.com/docker/extension-ideas/discussions" class="btn">Submit Your Docker Extensions Ideas</a>
      {% endif %}
    </header>

    <main id="content" class="main-content" role="main">
      {{ content }}
      <footer class="site-footer">
        <!-- Footer widgets and credits -->
      </footer>
    </main>
  </body>
</html>
```

### Using the Layout in a Page

Add front matter to any Markdown file:

```markdown
---
layout: default
title: My Page Title
description: Optional short description
---

# My Page

Content goes here.
```

### Customization Points

- `site.google_analytics`: When present, loads gtag. Define in `_config.yml`.
- `site.github.*`: GitHub Pages exposes repository metadata automatically; used for buttons and links.
- `site.show_downloads`: Toggles an extra CTA button in the header.
- `{{ content }}`: Slot where the page body is rendered.

If you need additional shared UI, add it to `_layouts/default.html` or create new layouts and reference them in page front matter.