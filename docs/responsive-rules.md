# Responsive Rules

Every template and Code Component in this workspace must work correctly on
desktop, tablet, and mobile. Framer's built-in breakpoint system handles most
of this — custom CSS breakpoints should be the exception, not the rule.

---

## Breakpoint table

| Breakpoint | Min width | Max width | Target device              |
|-----------|-----------|-----------|----------------------------|
| Desktop   | 1200px    | —         | Laptops, external monitors |
| Tablet    | 810px     | 1199px    | iPads, large phones (landscape) |
| Mobile    | 0px       | 809px     | Smartphones (portrait)     |

These match Framer's default breakpoints. Align all responsive behaviour to
these values.

## Reference widths (for design comps & testing)

| Width       | Use for…                                  |
|-------------|-------------------------------------------|
| 1440px      | Desktop design reference                  |
| 810px       | Tablet design reference (lower bound)     |
| 390px       | Mobile design reference (iPhone 14)       |
| 375px       | Mobile design reference (iPhone SE)       |
| 428px       | Mobile design reference (iPhone 14 Pro Max)|

---

## Primary responsive strategy: Stack direction flip

Framer's `Stack` component is the first (and often only) responsive tool you
need. The rule:

> A horizontal Stack on desktop **must** flip to vertical on mobile — either
> via a Framer breakpoint override on the Stack's direction property, or via a
> custom Code Component that reads the viewport.

```tsx
// Inside a Code Component — reading Framer's responsive context
import { useBreakpoint } from "framer"

function MyComponent() {
    const breakpoint = useBreakpoint()
    const isMobile = breakpoint === "mobile"

    return (
        <div style={{ display: "flex", flexDirection: isMobile ? "column" : "row", gap: 24 }}>
            {/* children */}
        </div>
    )
}
```

Prefer a native Stack (with breakpoint overrides set in the Framer UI) over
this approach unless the component genuinely needs programmatic layout control.

---

## Responsive patterns

### Pattern 1: Stack wrap (preferred)

Use a horizontal Stack with `wrap: true` and set min/max widths on children.
Items flow into rows naturally — no direction flip needed.

**Best for:** card grids, tag lists, icon rows, feature grids.

### Pattern 2: Direction flip

Horizontal Stack on desktop → vertical Stack on tablet/mobile.

**Best for:** hero sections (text + image), two-column layouts, feature
alternating rows, footer columns.

### Pattern 3: Hide / show

Hide non-essential elements on mobile; show a simplified alternative.

**Best for:** large hero illustrations, decorative elements, secondary
navigation, complex data tables (show cards instead).

### Pattern 4: CSS Grid with auto-fit

Only in Code Components where Stack cannot express the layout.

```css
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: var(--space-6);
}
```

**Best for:** complex card grids where item count varies, dashboard layouts,
masonry-style galleries.

### Pattern 5: Overflow scroll

On mobile, collapse a wide element into a horizontally scrollable container.

**Best for:** data tables, tab bars with many items, logo clouds, pricing
table comparisons.

---

## Responsive typography

Use Framer's text style breakpoint overrides for headings and body text.
Reference values:

| Element      | Desktop      | Tablet       | Mobile       |
|-------------|-------------|-------------|-------------|
| Hero heading | `--text-5xl` | `--text-4xl` | `--text-3xl` |
| Page heading | `--text-3xl` | `--text-2xl` | `--text-2xl` |
| Section heading | `--text-2xl` | `--text-xl` | `--text-xl` |
| Body         | `--text-base` | `--text-base` | `--text-base` |
| Caption      | `--text-sm`   | `--text-sm`  | `--text-xs`  |

---

## Responsive spacing

Reduce section-level spacing on narrower breakpoints:

| Token          | Desktop  | Tablet   | Mobile   |
|----------------|----------|----------|----------|
| `--space-20`   | 80px     | 64px     | 48px     |
| `--space-16`   | 64px     | 48px     | 40px     |
| `--space-12`   | 48px     | 40px     | 32px     |
| `--space-8`    | 32px     | 24px     | 24px     |
| `--space-6`    | 24px     | 20px     | 16px     |

These overrides should be applied via Framer's breakpoint system on Stack
`gap` and Frame `padding`, not via custom code.

---

## Testing checklist

For every template and component, verify on all three breakpoints:

- [ ] No horizontal overflow (no unwanted scroll bar).
- [ ] All text remains readable (no truncation unless intentional).
- [ ] Touch targets are at least 44×44px on mobile.
- [ ] Images scale within their containers (no fixed pixel widths that break out).
- [ ] Navigation is usable (mobile menu or simplified nav shown).
- [ ] Forms and inputs remain usable (full-width on mobile).
- [ ] No content is permanently hidden on mobile unless a clear alternative is shown.

---

## Anti-patterns

Avoid these in responsive work:

- ❌ Fixed pixel widths on containers (`width: 1200px`).
- ❌ Custom `@media` queries at widths that don't match Framer's breakpoints.
- ❌ Desktop-only hover interactions without a tap fallback.
- ❌ `overflow: hidden` that clips content instead of reflowing it.
- ❌ Text that shrinks below 12px on any breakpoint.
- ❌ Images with `object-fit: cover` on critical content (faces, logos) without
  checking the crop on every breakpoint.
