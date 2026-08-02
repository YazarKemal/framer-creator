# Template Structure

Every template in this workspace follows a consistent directory layout so that
assets, metadata, and exports are predictable and easy to automate.

## Directory layout

```
templates/<template-name>/
├── README.md            # Human-readable template description
├── framer.json          # Machine-readable manifest
├── assets/              # Template-specific static assets
│   ├── preview.png      # Primary Marketplace preview (2400×1600)
│   ├── thumbnail.png    # Marketplace card thumbnail (800×600)
│   └── screenshots/     # Additional gallery screenshots
│       ├── 01.png
│       ├── 02.png
│       └── ...
├── export/              # Framer project export (from Framer → File → Export)
│   └── project.framerfx
└── overrides/           # Custom Code Component overrides (optional)
    └── ...
```

## `framer.json` manifest

Every template MUST include a valid `framer.json` at its root. This is the
machine-readable metadata that Framer reads when publishing to the
Marketplace.

```jsonc
{
    // Required
    "name": "My Template",                // Display name (max 60 chars)
    "description": "A short pitch.",       // Display description (max 300 chars)
    "version": "1.0.0",                    // SemVer
    "category": "marketing",               // See categories table below
    "tags": ["landing-page", "dark"],      // 2–6 tags

    // Optional but strongly recommended
    "author": "Your Name",
    "requiresPaidPlan": false,             // true if template uses paid features
    "minFramerVersion": "2024.1",
    "previewUrl": "https://your-site.framer.website/",

    // Component listing (for component-only templates)
    "components": [
        {
            "name": "HeroBanner",
            "file": "components/HeroBanner.tsx",
            "description": "A full-width hero with CTA."
        }
    ]
}
```

## Template categories

| Category key     | Marketplace label         |
|------------------|---------------------------|
| `marketing`      | Marketing                 |
| `saas`           | SaaS                      |
| `portfolio`      | Portfolio / Personal      |
| `blog`           | Blog / Editorial          |
| `ecommerce`      | Ecommerce                 |
| `agency`         | Agency                    |
| `startup`        | Startup                   |
| `event`          | Event / Conference        |
| `docs`           | Documentation             |
| `component`      | Component-only (no pages) |

## Preview image specs

| Asset               | Dimensions  | Format | Max size |
|----------------------|-------------|--------|----------|
| Primary preview      | 2400 × 1600 | PNG    | 5 MB     |
| Thumbnail            | 800 × 600   | PNG    | 1 MB     |
| Gallery screenshot   | 2400 × 1600 | PNG    | 5 MB     |

Use 2× resolution for all previews. Framer displays previews at 1200×800
(primary) and 400×300 (thumbnail), so 2× ensures sharp rendering on high-DPI
screens.

## Component-only vs full templates

A **full template** ships complete page layouts — at minimum a landing page
and one inner page. It uses the full directory structure above.

A **component-only template** ships one or more Code Components without page
layouts. Its `framer.json` sets `"category": "component"` and lists each
component in the `"components"` array. It may omit the `export/` directory
if no Framer project file is needed.

## Naming conventions

- Directory names: lowercase kebab-case (`landing-page-pro`, `saas-dashboard`)
- Component file names: PascalCase (`HeroBanner.tsx`, `PricingTable.tsx`)
- Asset file names: lowercase kebab-case with numeric ordering (`hero-desktop.png`,
  `screenshot-01.png`)
- JSON keys: camelCase (`minFramerVersion`, `requiresPaidPlan`)
