# Framer Creator

A professional workspace for building high-quality
[Framer Marketplace](https://www.framer.com/marketplace/) templates and Code
Components.

---

## What is this?

This repository is a disciplined, repeatable environment for creating Framer
assets that customers can purchase, remix, and publish. It enforces the
constraints of the Framer platform — components must be self-contained,
templates must be visually editable, and every artifact must meet Marketplace
quality standards.

**This is not a standalone website.** Everything produced here is designed to
be assembled, previewed, and published inside the Framer editor.

## Repository structure

```
framer-creator/
├── assets/            Static assets shared across templates
├── components/        Framer Code Components (React + TypeScript)
├── docs/              Project documentation and reference material
├── prompts/           Reusable AI prompts for generation workflows
└── templates/         Framer template source files and exports
```

## Philosophy

- **Native Framer first.** Use Framer's built-in layout primitives (Stack,
  Grid, Section) whenever possible. Write custom code only when Framer cannot
  express the design alone.
- **Responsive by default.** Every component and template works on desktop,
  tablet, and mobile — using Framer's breakpoint system, not hand-rolled media
  queries.
- **Marketplace quality.** Every artifact follows Framer's acceptance criteria:
  clean visuals, accessible markup, performant code, and clear defaults.
- **Designer-friendly.** Property Controls use plain language. Defaults are
  sensible. Documentation assumes no coding knowledge on the customer's side.
- **Minimal dependencies.** Every kilobyte matters in a Framer Code Component.
  Prefer the platform over packages.

## Getting started

### Prerequisites

- A [Framer](https://www.framer.com/) account
- Node.js 18+ and pnpm (for local component development)
- Familiarity with React, TypeScript, and the Framer editor

### Creating a Code Component

1. Duplicate `components/_template.tsx` (once it exists) into
   `components/YourComponent.tsx`.
2. Fill in the props, component body, and property controls.
3. Copy the compiled output into a Framer Code Component override.

### Creating a Template

1. Design the layout inside the Framer editor using native components.
2. Export the project into `templates/<your-template>/export/`.
3. Add a `framer.json` manifest and `README.md`.
4. Submit to the Framer Marketplace.

## Documentation

| Document                              | What it covers                          |
|---------------------------------------|-----------------------------------------|
| `docs/template-structure.md`          | Directory layout and manifest spec      |
| `docs/design-tokens.md`               | Colour, spacing, typography tokens      |
| `docs/responsive-rules.md`            | Breakpoints and responsive patterns     |
| `docs/marketplace-checklist.md`       | Framer Marketplace acceptance criteria  |

## License

This workspace is intended for creating commercial Framer Marketplace assets.
Individual templates and components may carry their own license terms — see
the README inside each directory for details.

---

**Built for the Framer Marketplace.**
