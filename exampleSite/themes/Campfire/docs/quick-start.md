# Campfire Theme — Quick Start

A warm, story-focused Hugo theme. This guide helps you get running fast.

## Requirements
- Hugo Extended (latest recommended)
- Git

## Install
```bash
# as a git submodule (recommended)
git submodule add https://github.com/yourname/Campfire-Hugo-Theme themes/Campfire
```
In your site `config.toml`:
```toml
theme = "Campfire"
# Only for local theme dev via exampleSite:
# themesDir = "../"
```

## Run locally
```bash
hugo server -D
```
Visit http://localhost:1313.

## Core configuration
```toml
baseURL = "https://example.com/"
title = "My Campfire Blog"
paginate = 10

taxonomies = { tag = "tags", category = "categories" }

[params]
  description = "Where great stories find their home."
  ogDefaultImage = "/images/og-default.jpg"

[author]
  name = "Your Name"

[params.social]
  twitter = "yourhandle"         # without @
  twitter_card = "summary_large_image"

[params.campfire]
  version = "1.0.0"

[params.campfire.storytelling]
  # Modes: daylight, firelight, auto
  mode = "auto"
  # Font pairs: storyteller, explorer, adventurer
  fontPair = "storyteller"
  # Layout presets: circle (default), corner, clearing
  layout = "circle"

[params.campfire.gathering]
  sidebar = true
  newsletter = false
  search = false
```

## Creating posts
Use the included archetype for consistent front matter:
```bash
hugo new posts/my-first-story.md
```
Front matter fields:
```yaml
---
title: "My First Story"
description: "A brief description for SEO and cards"
date: 2025-08-20
tags: ["campfire", "intro"]
categories: ["journal"]
images: ["/images/cover.jpg"]
author: "Your Name"
draft: true
---
```

## Features you get out of the box
- Accessible base: skip link, visible focus, reduced motion support
- Daylight/Firelight theming with auto-switching
- Sidebar (Storyteller’s Corner) with optional widgets
- Layout presets: circle, corner, clearing
- Post enhancements: reading time, taxonomy links, related tales
- SEO: canonical, Open Graph, Twitter cards, JSON-LD, default OG image
- Pagination on list pages

## Tips
- Set `images` in a post to customize OG/Twitter preview; falls back to `params.ogDefaultImage`.
- Tweak list pagination via `paginate` in config.
- Use categories for broad groupings and tags for specifics; both render as badges on lists.

## Deploy
```bash
hugo --minify
# Deploy the generated public/ directory to your host or CDN.
```

If you need help or want to suggest features, open an issue in the repo. Warm stories welcome.
