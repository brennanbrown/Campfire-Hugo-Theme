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

## Storytelling modes, layout, and fonts

The theme exposes a few presentation presets via `params.campfire.storytelling`:

```toml
[params.campfire.storytelling]
# Modes: "daylight" (light), "firelight" (dark), or "auto"
# When set to auto, the theme follows the user's system setting (prefers-color-scheme)
mode = "auto"

# Font pairs: storyteller (Crimson Pro + Inter), explorer (Lora + Source Sans 3), adventurer (Playfair Display + Open Sans)
fontPair = "storyteller"

# Layout: circle (balanced width), corner (narrower content), clearing (wider content)
layout = "circle"
```

Notes:
- In explicit modes (`daylight` or `firelight`), the body gets a class to force that scheme. In `auto`, it defers to the OS preference.
- Font pairs load the appropriate Google Fonts in `layouts/partials/head.html` and apply via CSS variables.
- You can toggle the sidebar and other widgets under `[params.campfire.gathering]`.

### Accessibility
- A "Skip to main content" link is rendered at the top of the page and becomes visible on focus.
- Visible `:focus-visible` outlines and reduced motion media query are included by default.

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
