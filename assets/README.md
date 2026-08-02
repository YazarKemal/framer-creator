# Assets

Static assets shared across templates and components — icons, images, fonts,
and other binary resources.

## Placeholder

Assets will be organised into subdirectories as the workspace grows:

```
assets/
├── icons/        # SVG and PNG icons
├── images/       # Stock photos, illustrations, backgrounds
├── fonts/        # Licensed font files for offline use
└── branding/     # Logos, watermarks, and brand marks
```

### Guidelines

- Prefer SVG for icons and logos (resolution-independent, small file size).
- Use PNG for previews and screenshots (see `docs/template-structure.md` for
  dimension specs).
- Only commit font files that are licensed for redistribution.
- Keep individual files under 5 MB. Use WebP or AVIF for large images.
