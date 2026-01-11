# Documentation Frontmatter Convention

To ensure consistency and enable future tooling, all Markdown files in `zenith-docs/` should include a minimal YAML frontmatter.

## Format

```yaml
---
title: "Page Title"
order: 1
version: "0.4.0" # Optional: defaults to latest
---
```

## Fields

- **`title`**: (Required) The human-readable title of the page used in the sidebar and `<title>` tag.
- **`order`**: (Optional) A numeric value to control the sorting of pages in the sidebar.
- **`version`**: (Optional) The specific version of Zenith this documentation applies to. If omitted, it is assumed to be for the most recent release.
