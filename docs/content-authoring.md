## Content Authoring Guide

This project’s primary content lives in the root `README.md` (extension listings) and under section folders like `faqs/`.

### Adding or Updating Extension Entries

Extension listings are grouped into category tables. To add an entry:

1. Find the relevant category section in the root `README.md` (e.g., `## Utilities`).
2. Add a new table row following the existing column order.

Example row format:

```markdown
| 25 | Example Extension | Short description | [Install](https://open.docker.com/extensions/marketplace?extensionId=org/name) | [Link](https://github.com/org/repo) | ![Github Stars](https://img.shields.io/github/stars/org/repo) |
```

Tips:

- Keep names concise. Use badges like `![badge](https://img.shields.io/badge/-new-red)` to denote new.
- Prefer stable links (Docker Hub for install, GitHub for code).
- Use standardized popularity badges where available.

### Adding a New Category

1. Create a new `## Heading` under "Categories" in `README.md`.
2. Insert a Markdown table with consistent columns.
3. Update the Table of Contents if needed.

### Adding or Editing FAQs

FAQs live under `faqs/`. To add a new question:

- Edit `faqs/README.md` and append:

```markdown
## Que:N Your question here?

Your concise answer here. Include code examples when helpful.
```

### Page Front Matter and Layout

For new Markdown pages, add front matter to use the default layout:

```markdown
---
layout: default
title: FAQs
description: Common questions about Docker Desktop Extensions
---

# FAQs

...content...
```

### Images and Badges

- Host images in a stable location (e.g., GitHub user-images or repo) and link via HTTPS.
- Use Shields.io badges for stars, pulls, etc., consistent with existing rows.

### Link Hygiene

- Avoid bare URLs; anchor text should describe the destination.
- Validate install links work in Docker Desktop (`open.docker.com/extensions/...`).