---
title: "Markdown Syntax Demo"
date: 2025-08-20T04:22:30-08:00
summary: "A quick tour of Markdown features as rendered by the Campfire theme."
categories: ["Guides"]
tags: ["markdown", "demo", "syntax"]
draft: false
---

# Heading 1
## Heading 2
### Heading 3

Paragraph with emphasis like *italics*, **bold**, and `inline code`.

> Blockquote: Stories told by the fire.

- Unordered list item
- Another item
  - Nested item

1. Ordered item
2. Another item

```bash
# Code block with language
hugo new posts/first-post.md
```

```toml
[params]
  description = "Example"
```

Table:

| Feature   | Status |
|-----------|--------|
| SEO       | ✅     |
| Pagination| ✅     |
| Modes     | 🚧     |

Image:

![Campfire](/images/og-default.jpg)

Horizontal rule:

---

Links: [Hugo](https://gohugo.io)

Footnote demo[^1].

[^1]: A cozy note by the fire.
