# Design Tokens

This document defines the design tokens used across all templates and
components in this workspace. Every visual decision — colour, spacing,
typography, radius, shadow — must reference a token from this catalogue.

Tokens are exposed as CSS custom properties. Code Components reference them
via `var(--token-name)`; Framer-native designs reference them through
Framer's colour and text style system (which maps to these tokens).

---

## Colour palette

### Brand

| Token                     | Hex       | Usage                        |
|---------------------------|-----------|------------------------------|
| `--color-brand-50`        | `#EEF2FF` | Brand tint (backgrounds)     |
| `--color-brand-100`       | `#D9E2FF` | Brand tint (hover states)    |
| `--color-brand-200`       | `#B3C5FF` | Brand tint (borders)         |
| `--color-brand-500`       | `#4F6EF7` | Primary brand                |
| `--color-brand-600`       | `#3B56E0` | Brand hover / active         |
| `--color-brand-700`       | `#2A3FBA` | Brand pressed / text-on-tint |
| `--color-brand-900`       | `#17206E` | Brand text / icons           |

### Neutral

| Token                     | Hex       | Usage                        |
|---------------------------|-----------|------------------------------|
| `--color-neutral-0`       | `#FFFFFF` | White / page background      |
| `--color-neutral-50`      | `#F8F9FC` | Subtle surface               |
| `--color-neutral-100`     | `#EDF0F5` | Surface / card background    |
| `--color-neutral-200`     | `#DEE2EB` | Borders / dividers           |
| `--color-neutral-300`     | `#C5CBD6` | Disabled / placeholder       |
| `--color-neutral-400`     | `#9BA3B0` | Muted text / icons           |
| `--color-neutral-500`     | `#6B7482` | Secondary text               |
| `--color-neutral-700`     | `#383F4B` | Body text                    |
| `--color-neutral-900`     | `#13161C` | Heading text                 |

### Semantic

| Token                     | Hex       | Usage                        |
|---------------------------|-----------|------------------------------|
| `--color-success-500`     | `#16A34A` | Success states               |
| `--color-success-100`     | `#DCFCE7` | Success background           |
| `--color-warning-500`     | `#F59E0B` | Warning states               |
| `--color-warning-100`     | `#FEF3C7` | Warning background           |
| `--color-error-500`       | `#EF4444` | Error states                 |
| `--color-error-100`       | `#FEE2E2` | Error background             |
| `--color-info-500`        | `#3B82F6` | Info states                  |
| `--color-info-100`        | `#DBEAFE` | Info background              |

---

## Spacing scale

A 4px-based scale. Use `--space-*` tokens (never raw `px` values) for
`padding`, `margin`, and `gap`.

| Token          | Value   | Use case                            |
|----------------|---------|-------------------------------------|
| `--space-0`    | 0px     | No space                            |
| `--space-1`    | 4px     | Tight inline spacing, icon-text gap |
| `--space-2`    | 8px     | Compact gaps                        |
| `--space-3`    | 12px    | Internal element spacing            |
| `--space-4`    | 16px    | Default component padding           |
| `--space-5`    | 20px    | Relaxed padding                     |
| `--space-6`    | 24px    | Section gutters, card padding       |
| `--space-8`    | 32px    | Section padding, stacked gap        |
| `--space-10`   | 40px    | Large section spacing               |
| `--space-12`   | 48px    | Section separators                  |
| `--space-16`   | 64px    | Major section spacing               |
| `--space-20`   | 80px    | Hero padding                        |
| `--space-24`   | 96px    | Page-level spacing                  |

---

## Typography

### Font families

| Token                | Value                                              | Usage          |
|----------------------|----------------------------------------------------|----------------|
| `--font-sans`        | `"Inter", system-ui, -apple-system, sans-serif`    | Body, UI       |
| `--font-display`     | `"Satoshi", "Inter", system-ui, sans-serif`        | Headings       |
| `--font-mono`        | `"JetBrains Mono", "Fira Code", monospace`         | Code, data     |

### Type scale

| Token              | Size / Leading | Font weight | Use case              |
|--------------------|---------------|-------------|-----------------------|
| `--text-xs`        | 12px / 16px   | 400         | Captions, labels      |
| `--text-sm`        | 14px / 20px   | 400         | Small body, help text |
| `--text-base`      | 16px / 24px   | 400         | Body text             |
| `--text-lg`        | 18px / 28px   | 400         | Large body, lead-ins  |
| `--text-xl`        | 20px / 28px   | 500         | Subheadings           |
| `--text-2xl`       | 24px / 32px   | 600         | Section headings      |
| `--text-3xl`       | 30px / 38px   | 700         | Page headings         |
| `--text-4xl`       | 36px / 44px   | 700         | Hero headings         |
| `--text-5xl`       | 48px / 56px   | 800         | Display headings      |
| `--text-6xl`       | 60px / 68px   | 800         | Large display         |

---

## Border radius

| Token             | Value  | Use case                           |
|-------------------|--------|------------------------------------|
| `--radius-none`   | 0px    | Sharp edges                        |
| `--radius-sm`     | 4px    | Inputs, badges, small containers   |
| `--radius-md`     | 8px    | Cards, buttons, modals             |
| `--radius-lg`     | 12px   | Large cards, panels                |
| `--radius-xl`     | 16px   | Hero sections, feature cards       |
| `--radius-full`   | 9999px | Pills, avatars, rounded buttons    |

---

## Box shadows

| Token               | Value                                                      | Use case               |
|---------------------|------------------------------------------------------------|------------------------|
| `--shadow-none`     | `none`                                                     | No shadow              |
| `--shadow-xs`       | `0 1px 2px rgba(19, 22, 28, 0.05)`                        | Subtle lift            |
| `--shadow-sm`       | `0 1px 3px rgba(19, 22, 28, 0.08), 0 1px 2px rgba(19, 22, 28, 0.06)` | Cards, buttons |
| `--shadow-md`       | `0 4px 8px rgba(19, 22, 28, 0.08), 0 2px 4px rgba(19, 22, 28, 0.06)` | Dropdowns, modals |
| `--shadow-lg`       | `0 12px 24px rgba(19, 22, 28, 0.08), 0 4px 8px rgba(19, 22, 28, 0.06)` | Elevated panels |
| `--shadow-xl`       | `0 20px 40px rgba(19, 22, 28, 0.10), 0 8px 16px rgba(19, 22, 28, 0.06)` | Hero overlays  |

---

## Using tokens

### In Code Components (CSS custom properties)

```tsx
<div
    style={{
        backgroundColor: "var(--color-brand-500)",
        padding: "var(--space-6)",
        borderRadius: "var(--radius-md)",
        fontFamily: "var(--font-sans)",
        fontSize: "var(--text-base)",
        boxShadow: "var(--shadow-sm)",
    }}
>
    Hello
</div>
```

### In Framer-native designs

Map these tokens to Framer's **Local Styles** (colour styles, text styles,
effect styles). Name the styles exactly as the token names appear above so the
mapping stays clear.

### Adding or changing a token

1. Update this file.
2. If a new token, propagate it to the Framer Local Styles of every active
   template that uses the affected group.
3. If changing an existing token value, audit all Code Components for the
   `var(--...)` reference — the change breaks nothing structurally, but the
   visual result must be reviewed.
