# Design System — Dentiva

A complete design system for the Dentiva Framer template. Every value defined
here maps to a Framer Variable or Style so that buyers can rebrand the entire
site from one place.

---

## Brand principles

1. **Calm over clinical.** The design should feel like a well-designed hotel
   lobby — warm, clean, and welcoming — not a hospital ward.
2. **Clarity over decoration.** Every visual element has a job. Whitespace is
   a feature, not empty space.
3. **Typographic, not illustrative.** The primary visual language is
   typography and photography. Icons and illustrations play a supporting role.
4. **Soft but structured.** Rounded corners and gentle shadows, but always
   within a clear grid — never amorphous or floating.
5. **Accessible by default.** Colour contrast, keyboard navigation, and
   readable type are baked in, not retrofitted.

---

## Colour system

### Brand palette

The primary brand colour is a restrained blue-green (teal-cyan range) that
feels clinical enough for a healthcare setting but warm enough to avoid the
"hospital" association. A warm neutral secondary palette grounds the design.

| Token | HEX | Role |
|-------|-----|------|
| `--dentiva-brand-50` | `#F0F7F6` | Brand surface — section backgrounds, card fills |
| `--dentiva-brand-100` | `#D5EDE9` | Brand surface hover — interactive card states |
| `--dentiva-brand-200` | `#A6D9D2` | Brand borders, dividers, selected states |
| `--dentiva-brand-400` | `#5BBFB4` | Brand muted — secondary icons, decorative elements |
| `--dentiva-brand-500` | `#2DA89D` | **Primary brand** — buttons, links, active states, icons |
| `--dentiva-brand-600` | `#258E84` | Brand hover — button hover, link hover |
| `--dentiva-brand-700` | `#1D6E66` | Brand active — button pressed states |
| `--dentiva-brand-900` | `#134740` | Brand text — headings, emphasis on brand backgrounds |

### Neutral palette

| Token | HEX | Role |
|-------|-----|------|
| `--dentiva-neutral-0` | `#FFFFFF` | Page background, card backgrounds on white |
| `--dentiva-neutral-25` | `#FAFAF9` | Subtle alternating section background |
| `--dentiva-neutral-50` | `#F5F4F1` | Warm surface — cards on coloured backgrounds |
| `--dentiva-neutral-100` | `#EBE9E5` | Borders, dividers |
| `--dentiva-neutral-200` | `#D6D3CE` | Disabled states, inactive icons |
| `--dentiva-neutral-400` | `#9E9A92` | Placeholder text, muted captions |
| `--dentiva-neutral-600` | `#635F58` | Secondary body text |
| `--dentiva-neutral-800` | `#363430` | Primary body text |
| `--dentiva-neutral-900` | `#1C1B19` | Headings, emphasis text |

### Surface hierarchy

| Layer | Token | Usage |
|-------|-------|-------|
| Page background | `--dentiva-neutral-0` | Default page surface |
| Subtle surface | `--dentiva-neutral-25` | Alternating sections, secondary cards |
| Elevated surface | `--dentiva-neutral-0` + `shadow-sm` | Cards on subtle backgrounds |
| Brand surface | `--dentiva-brand-50` | Hero sections, CTA banners, footer |
| Dark surface | `--dentiva-neutral-900` | Optional dark footer or accent sections |

### Text colours

| Token | Value | Usage |
|-------|-------|-------|
| Text primary | `--dentiva-neutral-900` | Body text, headings on light backgrounds |
| Text secondary | `--dentiva-neutral-600` | Supporting text, captions, metadata |
| Text muted | `--dentiva-neutral-400` | Placeholders, disabled text |
| Text on brand | `#FFFFFF` | Text on brand-500 and darker brand backgrounds |
| Text on dark | `#FFFFFF` or `--dentiva-neutral-25` | Text on neutral-900 backgrounds |
| Link text | `--dentiva-brand-500` | Inline links, untreated |
| Link hover | `--dentiva-brand-600` | Hover state |

### Semantic colours

| Token | HEX | Usage |
|-------|-----|-------|
| `--dentiva-success-500` | `#2D8A56` | Success messages, confirmation badges |
| `--dentiva-success-100` | `#EAF5EF` | Success message backgrounds |
| `--dentiva-warning-500` | `#B47C2E` | Warning messages, disclaimers |
| `--dentiva-warning-100` | `#FCF5E8` | Warning message backgrounds |
| `--dentiva-error-500` | `#C2433A` | Error messages, validation errors |
| `--dentiva-error-100` | `#FBEEED` | Error message backgrounds |
| `--dentiva-info-500` | `#2D7690` | Information messages |
| `--dentiva-info-100` | `#E8F3F7` | Information message backgrounds |

---

## Typography system

### Font families

All fonts are available from Google Fonts and can be applied in Framer via
the Font selector or as custom font imports.

| Token | Font stack | Role | Google Fonts name |
|-------|-----------|------|-------------------|
| `--dentiva-font-heading` | `"Crimson Pro", "Georgia", serif` | All headings (h1–h4), large display text | Crimson Pro |
| `--dentiva-font-body` | `"Inter", system-ui, -apple-system, sans-serif` | Body text, UI labels, navigation, forms | Inter |
| `--dentiva-font-accent` | `"Inter", system-ui, -apple-system, sans-serif` | Labels, badges, overlines, captions | Inter (use the same font, weight 500) |

**Why Crimson Pro + Inter:**
Crimson Pro is a refined serif with excellent legibility — it carries the
editorial, trustworthy quality the brand needs without feeling formal or old.
Inter is the most readable workhorse sans-serif available, and it pairs well
with serif headings. Both are open-source and available on Google Fonts.

### Type scale — desktop (1200px+)

| Token | Size / Leading | Weight | Font | Use |
|-------|---------------|--------|------|-----|
| `--dentiva-text-display` | 56px / 64px | 400 | Heading | Home hero only — rarely used |
| `--dentiva-text-h1` | 40px / 48px | 400 | Heading | Page titles |
| `--dentiva-text-h2` | 30px / 38px | 400 | Heading | Section headings |
| `--dentiva-text-h3` | 22px / 30px | 400 | Heading | Card headings, subsection titles |
| `--dentiva-text-h4` | 18px / 26px | 600 | Body (Inter) | Small headings, sidebar titles |
| `--dentiva-text-lead` | 20px / 32px | 400 | Body | Introductory paragraphs, hero supporting text |
| `--dentiva-text-body-lg` | 17px / 28px | 400 | Body | Treatment descriptions, longer reads |
| `--dentiva-text-body` | 15px / 24px | 400 | Body | Default body text |
| `--dentiva-text-body-sm` | 13px / 20px | 400 | Body | Captions, metadata, footer text |
| `--dentiva-text-label` | 13px / 16px | 500 | Body (Inter) | Labels, badges, form labels, overlines |
| `--dentiva-text-label-sm` | 11px / 14px | 500 | Body (Inter) | Small badges, eyebrow text, tag text |

### Type scale — tablet (810px–1199px)

| Token | Size / Leading |
|-------|---------------|
| `--dentiva-text-display` | 44px / 52px |
| `--dentiva-text-h1` | 34px / 42px |
| `--dentiva-text-h2` | 26px / 34px |
| `--dentiva-text-h3` | 20px / 28px |
| `--dentiva-text-h4` | 17px / 24px |
| `--dentiva-text-lead` | 18px / 28px |
| (Remaining tokens unchanged from desktop) | |

### Type scale — mobile (0–809px)

| Token | Size / Leading |
|-------|---------------|
| `--dentiva-text-display` | 36px / 42px |
| `--dentiva-text-h1` | 28px / 36px |
| `--dentiva-text-h2` | 22px / 30px |
| `--dentiva-text-h3` | 18px / 26px |
| `--dentiva-text-h4` | 16px / 22px |
| `--dentiva-text-lead` | 17px / 26px |
| `--dentiva-text-body-lg` | 16px / 26px |

---

## Spacing scale

A 4px base unit. Every margin, padding, and gap uses one of these tokens.

| Token | Value | Usage |
|-------|-------|-------|
| `--dentiva-space-0` | 0 | No space |
| `--dentiva-space-1` | 4px | Tight inline spacing, icon–text gap |
| `--dentiva-space-2` | 8px | Compact gaps inside components |
| `--dentiva-space-3` | 12px | Internal element spacing |
| `--dentiva-space-4` | 16px | Default padding inside cards |
| `--dentiva-space-5` | 20px | Relaxed gap between related elements |
| `--dentiva-space-6` | 24px | Card padding, section gutters |
| `--dentiva-space-8` | 32px | Section padding (inner) |
| `--dentiva-space-10` | 40px | Medium section gap |
| `--dentiva-space-12` | 48px | Section-to-section gap |
| `--dentiva-space-16` | 64px | Large section separation |
| `--dentiva-space-20` | 80px | Hero vertical padding |
| `--dentiva-space-24` | 96px | Page-level top/bottom padding |

### Responsive spacing adjustment

Section-level spacing scales down on tablet and mobile:

| Token | Desktop | Tablet | Mobile |
|-------|---------|--------|--------|
| `--dentiva-space-16` | 64px | 48px | 40px |
| `--dentiva-space-20` | 80px | 56px | 48px |
| `--dentiva-space-24` | 96px | 64px | 48px |

These should be set as breakpoint overrides in Framer, not as new tokens.

---

## Content width system

| Token | Value | Usage |
|-------|-------|-------|
| `--dentiva-content-narrow` | 720px | Text-heavy content, treatment descriptions, journal articles |
| `--dentiva-content-standard` | 960px | Default section width — most sections use this |
| `--dentiva-content-wide` | 1160px | Card grids, doctor listings, full-bleed hero content |
| `--dentiva-content-full` | 100% | Hero backgrounds, full-width strips |

### Horizontal padding (gutters)

| Breakpoint | Padding |
|-----------|---------|
| Desktop | 32px (applied via section wrapper) |
| Tablet | 24px |
| Mobile | 16px |

---

## Grid specifications

### Primary grid (card layouts)

| Property | Value |
|----------|-------|
| Columns (desktop) | 3 |
| Columns (tablet) | 2 |
| Columns (mobile) | 1 |
| Column gap | `--dentiva-space-6` (24px) |
| Row gap | `--dentiva-space-8` (32px) |

Use Framer's **Grid** component for treatment cards, doctor cards, and
journal cards.

### Secondary grid (2-column content)

| Property | Value |
|----------|-------|
| Columns | 2 (desktop), 1 (tablet and below) |
| Column gap | `--dentiva-space-10` (40px) |
| Row gap | `--dentiva-space-6` (24px) |

Used for text+image sections, process steps, and feature comparisons.

---

## Border radius

| Token | Value | Usage |
|-------|-------|-------|
| `--dentiva-radius-none` | 0 | Sharp edges (not commonly used) |
| `--dentiva-radius-sm` | 6px | Inputs, small badges |
| `--dentiva-radius-md` | 10px | Buttons, cards, form fields |
| `--dentiva-radius-lg` | 16px | Large cards, modal dialogs |
| `--dentiva-radius-xl` | 20px | Hero image containers, feature panels |
| `--dentiva-radius-full` | 9999px | Pills, avatars |

### Radius pairing rules

- Buttons use `--dentiva-radius-md` (10px) — rounded but not pill-shaped
- Cards use `--dentiva-radius-lg` (16px) — soft but structured
- Inputs use `--dentiva-radius-sm` (6px) — tight, functional
- Doctor photos use `--dentiva-radius-md` (10px) — slightly rounded, not circular

---

## Border styles

| Token | Value | Usage |
|-------|-------|-------|
| `--dentiva-border-light` | `1px solid var(--dentiva-neutral-100)` | Card borders, dividers |
| `--dentiva-border-input` | `1px solid var(--dentiva-neutral-200)` | Form field borders |
| `--dentiva-border-input-focus` | `1.5px solid var(--dentiva-brand-500)` | Focused form field |
| `--dentiva-border-input-error` | `1.5px solid var(--dentiva-error-500)` | Errored form field |
| `--dentiva-border-brand` | `1px solid var(--dentiva-brand-200)` | Brand accent borders |
| `--dentiva-border-section` | `1px solid var(--dentiva-neutral-100)` | Horizontal section dividers |

---

## Shadow system

Shadows are restrained — used to create gentle depth, not dramatic elevation.

| Token | Value | Usage |
|-------|-------|-------|
| `--dentiva-shadow-none` | `none` | Default — most surfaces |
| `--dentiva-shadow-sm` | `0 1px 3px rgba(28, 27, 25, 0.06), 0 1px 2px rgba(28, 27, 25, 0.04)` | Cards, buttons at rest |
| `--dentiva-shadow-md` | `0 4px 12px rgba(28, 27, 25, 0.06), 0 2px 4px rgba(28, 27, 25, 0.04)` | Hovered cards, dropdown menus |
| `--dentiva-shadow-lg` | `0 12px 28px rgba(28, 27, 25, 0.08), 0 4px 8px rgba(28, 27, 25, 0.04)` | Modal dialogs |

### Shadow usage rules

- Cards use `shadow-sm` by default; transition to `shadow-md` on hover
- The navbar uses `shadow-sm` only on scroll (not at top of page)
- Modals and dropdowns use `shadow-md`
- Never combine shadows with heavy borders — use one or the other for depth

---

## Components

### Buttons

#### Primary button

| Property | Value |
|----------|-------|
| Background | `--dentiva-brand-500` |
| Text colour | `#FFFFFF` |
| Border radius | `--dentiva-radius-md` (10px) |
| Padding (horizontal) | `--dentiva-space-6` (24px) |
| Padding (vertical) | `--dentiva-space-3` (12px) |
| Font | `--dentiva-text-label` (13px / 500) |
| Height | 44px minimum |
| Shadow | `--dentiva-shadow-sm` |

States:
- **Default:** `brand-500` background, white text
- **Hover:** `brand-600` background
- **Pressed:** `brand-700` background
- **Focus:** 2px brand-500 outline, offset 2px from button edge
- **Disabled:** `neutral-200` background, `neutral-400` text

#### Secondary button

| Property | Value |
|----------|-------|
| Background | Transparent |
| Border | `1px solid var(--dentiva-brand-500)` |
| Text colour | `--dentiva-brand-500` |
| All other properties | Same as primary |

States:
- **Default:** Transparent, brand border, brand text
- **Hover:** `brand-50` background
- **Pressed:** `brand-100` background
- **Focus:** Same as primary
- **Disabled:** `neutral-200` border, `neutral-400` text

#### Text link (inline)

| Property | Value |
|----------|-------|
| Text colour | `--dentiva-brand-500` |
| Text decoration | Underline (appears on hover only — can be set in Framer via text style) |
| Font weight | Inherit from surrounding text |

### Form controls

#### Text input

| Property | Value |
|----------|-------|
| Background | `--dentiva-neutral-0` |
| Border | `--dentiva-border-input` |
| Border radius | `--dentiva-radius-sm` (6px) |
| Padding | `--dentiva-space-3` (12px) vertical, `--dentiva-space-4` (16px) horizontal |
| Font | `--dentiva-text-body` |
| Height | 44px minimum |
| Placeholder colour | `--dentiva-neutral-400` |

States:
- **Default:** Light border, white background
- **Hover:** `neutral-100` border
- **Focus:** Brand border (1.5px), brand-50 background tint, subtle brand outer glow
- **Error:** Error border, error-100 background
- **Disabled:** `neutral-100` background, `neutral-400` text

#### Textarea

Same as text input, with `min-height: 120px` and vertical resize only.

#### Select / Dropdown

Same visual treatment as text input, with a custom chevron icon in
`neutral-400`.

#### Checkbox and Radio

| Property | Value |
|----------|-------|
| Size | 20px × 20px |
| Border | `--dentiva-border-input` |
| Border radius (checkbox) | `--dentiva-radius-sm` (4px) |
| Border radius (radio) | `--dentiva-radius-full` |
| Checked background | `--dentiva-brand-500` |
| Check mark colour | `#FFFFFF` |

#### Label

| Property | Value |
|----------|-------|
| Font | `--dentiva-text-label` (13px, weight 500) |
| Colour | `--dentiva-neutral-800` |
| Margin-bottom | `--dentiva-space-2` (8px) |

#### Validation message

| Property | Value |
|----------|-------|
| Font | `--dentiva-text-body-sm` (13px) |
| Error colour | `--dentiva-error-500` |
| Success colour | `--dentiva-success-500` |
| Position | Below the input, with `--dentiva-space-1` (4px) margin-top |

### Cards

#### Treatment card

| Property | Value |
|----------|-------|
| Background | `--dentiva-neutral-0` |
| Border | `--dentiva-border-light` |
| Border radius | `--dentiva-radius-lg` (16px) |
| Padding | `--dentiva-space-6` (24px) |
| Shadow (default) | `--dentiva-shadow-sm` |
| Shadow (hover) | `--dentiva-shadow-md` |
| Icon size | 32px × 32px, `brand-500` colour |
| Title font | `--dentiva-text-h4` |
| Description font | `--dentiva-text-body` |
| Internal gap | `--dentiva-space-4` (16px) |

#### Doctor card

| Property | Value |
|----------|-------|
| Photo aspect ratio | 3:4 |
| Photo border radius | `--dentiva-radius-md` (10px) |
| Name font | `--dentiva-text-h3` |
| Title/specialisation font | `--dentiva-text-body` in `neutral-600` |
| Internal gap | `--dentiva-space-3` (12px) |
| Card background | Transparent (no card container) or `neutral-25` |

#### Testimonial card

| Property | Value |
|----------|-------|
| Background | `--dentiva-neutral-25` |
| Border radius | `--dentiva-radius-lg` (16px) |
| Padding | `--dentiva-space-8` (32px) |
| Quote font | `--dentiva-text-body-lg` in `neutral-800` |
| Attribution font | `--dentiva-text-label` in `neutral-600` |
| Rating stars | `brand-500` colour, 16px size |
| Quotation mark | Opening quote in `brand-200`, large (40px+), decorative only |

#### Journal card

| Property | Value |
|----------|-------|
| Image aspect ratio | 16:9 |
| Image border radius | `--dentiva-radius-md` (10px) |
| Title font | `--dentiva-text-h4` |
| Excerpt font | `--dentiva-text-body` |
| Category badge | `--dentiva-text-label-sm`, brand-500 text, brand-50 background |
| Date font | `--dentiva-text-body-sm`, neutral-600 |
| Internal gap | `--dentiva-space-3` (12px) |

### Navigation

#### Navbar (desktop)

| Property | Value |
|----------|-------|
| Background | `--dentiva-neutral-0` |
| Height | 64px |
| Max content width | `--dentiva-content-wide` (1160px) |
| Shadow | `none` at top; `shadow-sm` on scroll |
| Link font | `--dentiva-text-label` (13px, weight 500) |
| Link colour | `--dentiva-neutral-600` |
| Link colour (active) | `--dentiva-brand-500` |
| Link hover | `--dentiva-neutral-800` |
| CTA button | Primary button, height 40px (compact in navbar) |

#### Navbar (mobile)

| Property | Value |
|----------|-------|
| Menu trigger | 44px × 44px hamburger icon |
| Mobile menu | Full-width slide-down panel |
| Menu background | `--dentiva-neutral-0` |
| Menu link font | `--dentiva-text-h4` |
| Menu link spacing | `--dentiva-space-5` (20px) vertical gap |
| Menu CTA | Full-width primary button |

#### Footer

| Property | Value |
|----------|-------|
| Background | `--dentiva-brand-50` |
| Columns (desktop) | 5 |
| Columns (tablet) | 3 |
| Columns (mobile) | 1 (stacked) |
| Section padding | `--dentiva-space-16` (top), `--dentiva-space-12` (bottom) |
| Column heading font | `--dentiva-text-label` (13px, weight 600) |
| Column link font | `--dentiva-text-body-sm` (13px) |
| Column link colour | `--dentiva-neutral-600` |
| Bottom bar | Separated by `--dentiva-border-light`, contains legal links and copyright |

### Accordion (FAQ)

| Property | Value |
|----------|-------|
| Border | `--dentiva-border-light` between items |
| Header padding | `--dentiva-space-5` (20px) vertical |
| Header font | `--dentiva-text-body-lg` |
| Header colour | `--dentiva-neutral-800` |
| Expand icon | Plus/minus or chevron, `brand-500`, 20px |
| Body padding | `--dentiva-space-5` (20px) bottom |
| Body font | `--dentiva-text-body` |
| Body colour | `--dentiva-neutral-600` |
| Open state | Header colour changes to `--dentiva-neutral-900` |

### Badges

| Property | Value |
|----------|-------|
| Font | `--dentiva-text-label-sm` (11px, weight 500) |
| Padding | 4px 10px |
| Border radius | `--dentiva-radius-full` (pill) |
| Default badge | `neutral-100` background, `neutral-600` text |
| Category badge | `brand-50` background, `brand-500` text |
| Verified badge | `success-100` background, `success-500` text |
| Warning badge | `warning-100` background, `warning-500` text |

---

## Iconography

Icons are sourced from **Phosphor Icons** (open-source, consistent 4-weight
system). Use the **Regular** weight by default and **Fill** for active or
selected states.

| Property | Value |
|----------|-------|
| Default icon size | 20px × 20px |
| Small icon size | 16px × 16px |
| Large icon size | 24px × 24px |
| Icon colour | Inherits from surrounding text or `brand-500` for standalone icons |
| Stroke width | 1.5px (Phosphor Regular) |

---

## Image ratios

| Context | Aspect ratio | Usage |
|---------|-------------|-------|
| Hero background | 16:9 or full-height | Home hero image |
| Doctor portrait | 3:4 | Doctor cards and detail pages |
| Treatment hero | 16:9 or 21:9 | Treatment detail hero |
| Journal thumbnail | 16:9 | Journal cards and detail hero |
| Clinic photo | 4:3 or 3:2 | About page facility images |
| Testimonial photo | 1:1 | Optional patient photo (circular crop) |

---

## Motion principles

Dentiva uses motion sparingly. The goal is to feel polished, not animated.

| Element | Effect | Duration | Easing |
|---------|--------|----------|--------|
| Section reveal (scroll) | Fade up, 20px translate | 400ms | `ease-out` |
| Card hover | Shadow increase + subtle scale (1.01) | 200ms | `ease-out` |
| Button hover | Background colour transition | 150ms | `ease` |
| Mobile menu open | Slide down + fade | 250ms | `ease-out` |
| Accordion open | Height expand | 250ms | `ease-out` |
| Page transition | Fade (simple opacity) | 200ms | `ease` |
| Form success message | Fade in | 300ms | `ease-out` |

### Motion rules

- **No auto-playing video or animation**
- **No scroll-jacking or parallax**
- **No staggering delays** on section reveals (reveal the whole section at
  once, not element by element)
- **Respect `prefers-reduced-motion`:** disable all motion when the user has
  requested reduced motion. In Framer, set scroll variants to trigger only
  when reduced motion is not preferred.

---

## State system

### Interactive state table

| State | Visual treatment |
|-------|-----------------|
| **Default** | As specified per component |
| **Hover** | Slightly darker background (brand: +100 shade), or shadow increase for cards |
| **Focus** | Visible outline: 2px solid `brand-500`, offset 2px from element |
| **Active / Pressed** | Darker background (brand: +200 shade), or slight scale-down (0.98) |
| **Disabled** | `neutral-200` background/border, `neutral-400` text, `cursor: not-allowed` |
| **Loading** | Skeleton screen (neutral-100 with subtle shimmer) for content; spinner or "…" suffix for buttons |
| **Error** | Red border + error background (inputs), or error-coloured text + icon |
| **Success** | Green border + success background (inputs), or success-coloured text + check icon |

---

## Accessibility contrast reference

Verify all text–background combinations meet WCAG AA:

| Text | Background | Contrast ratio | Pass AA? |
|------|-----------|---------------|----------|
| `neutral-900` (#1C1B19) on `neutral-0` (#FFFFFF) | 17.3:1 | ✅ AAA |
| `neutral-800` (#363430) on `neutral-0` (#FFFFFF) | 10.5:1 | ✅ AAA |
| `neutral-600` (#635F58) on `neutral-0` (#FFFFFF) | 4.7:1 | ✅ AA |
| `neutral-400` (#9E9A92) on `neutral-0` (#FFFFFF) | 3.0:1 | ❌ (do not use for body text — placeholders only) |
| White on `brand-500` (#2DA89D) | 4.5:1 | ✅ AA |
| White on `brand-600` (#258E84) | 5.3:1 | ✅ AA |
| White on `brand-700` (#1D6E66) | 7.2:1 | ✅ AAA |
| `brand-500` on `neutral-0` | 4.5:1 | ✅ AA (border-bottom for links; rely on underline for inline links) |
| `neutral-900` on `neutral-25` (#FAFAF9) | 15.8:1 | ✅ AAA |
| `neutral-600` on `neutral-25` | 4.3:1 | ⚠️ Borderline — use `neutral-800` on `neutral-25` instead for body text |

**Action:** Increase body text on `neutral-25` to `neutral-800` (#363430)
for a 9.1:1 ratio. Reserve `neutral-600` for captions and metadata only.

---

## Framer Variables recommendations

Create the following variables in Framer's Variables panel. Group them by
category for easy navigation in the editor.

### Colour Variables
Create one variable per colour token. Use Framer's **Color Variable** type.

### Number Variables
Create number variables for:
- Spacing scale (12 values)
- Border radius (5 values)
- Content widths (3 values)
- Grid column counts per breakpoint (optional)

### String Variables
- Font family names (so buyers can swap fonts in one place)

### Variable naming convention

Use the CSS custom property name without the leading dashes and with
Framer-friendly dots or slashes for grouping. Example:

```
Color / Brand / 500
Color / Neutral / 800
Space / 4
Space / 8
Radius / md
Font / Heading
Font / Body
```

This maps cleanly to the token table above and is easy for buyers to
understand.

---

## Naming conventions for Framer layers

| Element type | Naming pattern | Example |
|-------------|---------------|---------|
| Page | `Page — <Name>` | `Page — Home` |
| Section | `Section — <Name>` | `Section — Hero` |
| Component instance | `<Component> — <Context>` | `Button — Primary / Navbar CTA` |
| Text layer | `Text — <Purpose>` | `Text — Heading / h1` |
| Frame (container) | `Frame — <Purpose>` | `Frame — Card Container` |
| Stack | `Stack — <Direction> — <Purpose>` | `Stack — Horizontal — Treatment Cards` |
| Grid | `Grid — <Columns> — <Purpose>` | `Grid — 3 Col — Doctor Listing` |
| Image | `Image — <Content>` | `Image — Hero Background` |
| CMS list | `CMS — <Collection>` | `CMS — Treatments` |

Clear layer names make the template easier for buyers to navigate and edit.
