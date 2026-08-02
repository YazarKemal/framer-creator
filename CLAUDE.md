# CLAUDE.md — Framer Creator Workspace

## Overview

This workspace produces **Framer Marketplace templates** and **Framer Code
Components**. Every artifact here ends up inside the Framer editor, where
customers purchase, remix, and publish them.

The workspace is tooling-light by design. Framer handles layout, CMS, hosting,
and the visual editing experience — this repo exists for the code, assets, and
documentation that live *around* or *inside* those Framer projects.

## Repository map

```
framer-creator/
├── assets/            # Static assets shared across templates (icons, images, fonts)
├── components/        # Framer Code Components (React + TypeScript)
├── docs/              # Project-wide documentation and reference material
├── prompts/           # Reusable AI prompts for generating templates and components
├── templates/         # Template source files, configuration, and exports
├── CLAUDE.md          # This file
├── README.md          # Public-facing repository README
└── .gitignore
```

## Core constraints (read these first)

1. **This is NOT a standalone web app.** Do not scaffold Vite, Next.js,
   Create React App, or any other standalone bundler. Framer is the bundler,
   the renderer, and the host.

2. **Native Framer first.** Use Framer's built-in Stack, Grid, Text, Frame,
   and Section components for layout. Reach for custom React/TypeScript only
   when native Framer components cannot express the design efficiently.

3. **Every Code Component must be Framer-compatible.** This means:
   - Export a default function component (not a class, not a named export).
   - Wrap the component with `addPropertyControls` from `"framer"`.
   - Accept a `ComponentProps`-shaped props object (at minimum `style`).
   - Never rely on browser-only APIs without a guard (`typeof window !== "undefined"`).
   - Keep the component bundle small — no heavy dependencies.

4. **Property Controls are mandatory.** Every Code Component must expose
   useful controls so customers can customise it visually without touching
   code. Prefer `ControlType.String`, `ControlType.Boolean`,
   `ControlType.Number`, `ControlType.Color`, `ControlType.Image`,
   `ControlType.File`, `ControlType.Enum`, and
   `ControlType.ComponentInstance` over raw text inputs.

5. **Responsive by default.** Every template and component must work on:
   - Desktop (1440px reference)
   - Tablet (810px reference)
   - Mobile (390px reference)
   Use Framer's built-in breakpoint system; do not write custom media queries
   unless a Code Component genuinely needs them.

6. **No unnecessary dependencies.** Think twice before adding an npm package.
   Framer bundles dependencies into the component, so every KB matters for
   Marketplace performance. Prefer the platform (built-in DOM APIs, CSS) over
   libraries.

7. **Marketplace quality.** Everything here must meet Framer's acceptance
   criteria: clean UI, accessible markup, performant code, clear naming, and
   helpful defaults. See `docs/marketplace-checklist.md` for the full list.

## Component authoring pattern

Every Code Component follows this skeleton:

```tsx
import type { ComponentProps } from "react"
import { addPropertyControls, ControlType } from "framer"

// ── Props ────────────────────────────────────────────────────
interface Props extends ComponentProps {
    // Customisable properties here
    text?: string
    variant?: "primary" | "secondary"
}

// ── Component ────────────────────────────────────────────────
export default function MyComponent({ style, text, variant }: Props) {
    return (
        <div style={style}>
            <button className={`btn ${variant ?? "primary"}`}>
                {text ?? "Click me"}
            </button>
        </div>
    )
}

// ── Property Controls ────────────────────────────────────────
addPropertyControls(MyComponent, {
    text: {
        type: ControlType.String,
        title: "Text",
        defaultValue: "Click me",
    },
    variant: {
        type: ControlType.Enum,
        title: "Variant",
        options: ["primary", "secondary"],
        defaultValue: "primary",
    },
})
```

Rules for components:
- The file name in `components/` should match the component name in PascalCase
  (e.g. `components/HeroBanner.tsx`).
- Use only named `interface Props extends ComponentProps` — keep it explicit.
- Provide sensible `defaultValue` for every control.
- Use `title` strings that read naturally to a non-technical customer.
- Keep the component file self-contained. If a helper is reused across
  multiple components, extract it to `components/lib/`.

## Template authoring pattern

Templates live in `templates/<template-name>/`. Each template directory
contains:

```
templates/<template-name>/
├── README.md            # Description, preview image, feature list
├── framer.json          # Template manifest (name, tags, category, version)
├── assets/              # Template-specific assets (screenshots, icons)
└── export/              # Framer project export files
```

When creating a template:
1. Design the entire layout inside Framer using native components.
2. Export the Framer project into the `export/` directory.
3. Write a compelling README with at least one preview image.
4. Fill out `framer.json` completely — tags and category determine
   discoverability on the Marketplace.

## Design tokens

All design tokens are documented in `docs/design-tokens.md`. When building
components or templates, reference tokens by their CSS custom property names:

- `--color-*` — palette
- `--space-*` — spacing scale
- `--font-*` — typography
- `--radius-*` — border radii
- `--shadow-*` — box shadows

Do not hard-code colours or spacing values in components — every visual
decision must map back to a token.

## Responsive rules

See `docs/responsive-rules.md` for the full breakpoint matrix. Quick reference:

| Breakpoint | Min width | Target device      |
|-----------|-----------|--------------------|
| Desktop   | 1200px    | Laptops, monitors  |
| Tablet    | 810px     | iPads, large phones|
| Mobile    | 390px     | Smartphones        |

Use Framer's Stack `direction` flip (horizontal → vertical on narrower
breakpoints) as the primary responsive strategy. Reserve custom CSS for
complex reflows that Stack cannot express.

## Workflow — adding something new

### New Code Component
1. Create `components/<ComponentName>.tsx` following the skeleton above.
2. Add a row to the table in `components/README.md`.
3. (Optional) Add a companion prompt stub in `prompts/`.

### New Template
1. Scaffold `templates/<template-name>/` with the directory structure above.
2. Create `framer.json` and `README.md`.
3. Add a row to the table in `templates/README.md` (placeholder for now).

### New doc
1. Add the `.md` file to `docs/`.
2. If it's a first-class reference, link it from this CLAUDE.md under
   a relevant heading.

## Tone & audience

- Marketplace customers range from designers with zero coding experience to
  developers who prefer visual tools. Write property control titles and
  documentation for the broadest possible audience.
- Code comments should explain *why*, not *what*.
- README files should be warm, professional, and practical — show a preview,
  list features, and tell the customer what they're getting.

## References

- `docs/template-structure.md` — full template directory spec
- `docs/design-tokens.md` — token catalogue
- `docs/responsive-rules.md` — breakpoints and responsive patterns
- `docs/marketplace-checklist.md` — Framer Marketplace acceptance criteria
