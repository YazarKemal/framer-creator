# Marketplace Quality Checklist

Use this checklist before submitting any template or Code Component to the
Framer Marketplace. Every item must be satisfied for the submission to leave
this workspace.

---

## Code Components

### Structure & compatibility

- [ ] Component is the **default export** of its file.
- [ ] Component accepts `ComponentProps` (at minimum `style`).
- [ ] `addPropertyControls` is called with every controllable prop.
- [ ] No reliance on `window` / `document` without a `typeof window !== "undefined"` guard.
- [ ] Component has zero external runtime dependencies beyond `react` and
  `framer` (which Framer provides).
- [ ] File size is under 50 KB (unminified). Smaller is better.

### Property Controls

- [ ] Every prop that a customer might customise has a Property Control.
- [ ] Every control has a human-readable `title`.
- [ ] Every control has a sensible `defaultValue`.
- [ ] Enum controls use descriptive option labels (not internal keys).
- [ ] Image and File controls use appropriate types (`ControlType.Image`,
  `ControlType.File`).
- [ ] Controls are ordered logically (content first, then style, then advanced).

### Visual quality

- [ ] Component renders without visual errors at all three breakpoints.
- [ ] Text fits within its container (no overflow clipping).
- [ ] Interactive elements have visible hover, focus, and active states.
- [ ] Focus order follows a logical tab sequence.
- [ ] Colour contrast meets WCAG AA (4.5:1 for normal text, 3:1 for large text).

### Responsive behaviour

- [ ] Desktop (1440px): layout is correct, no stretching.
- [ ] Tablet (810px): layout adapts, no horizontal scroll.
- [ ] Mobile (390px): layout stacks vertically, touch targets are ≥ 44×44px.
- [ ] No content is permanently hidden without an alternative.

### Performance

- [ ] Component renders in under 16ms (no jank at 60fps).
- [ ] No unnecessary re-renders (memoize callbacks and derived values where
  appropriate).
- [ ] Images use appropriate dimensions (no 4000px images scaled to 200px in
  the browser).
- [ ] No synchronous blocking operations in render.

### Naming & documentation

- [ ] File name is PascalCase and matches the component name.
- [ ] Component has a JSDoc comment block describing what it does.
- [ ] README row is filled in (description, props table, preview image).
- [ ] Property Control titles use plain, customer-facing language.

---

## Templates

### Structure

- [ ] Directory follows the `template-structure.md` spec.
- [ ] `framer.json` is present and valid (all required fields filled).
- [ ] Preview image and thumbnail are the correct dimensions.
- [ ] `export/` directory contains a valid Framer project file.

### Design quality

- [ ] Design is cohesive — consistent use of colour, typography, spacing.
- [ ] Design tokens from `design-tokens.md` are used throughout (no ad-hoc
  values).
- [ ] At least one page is fully designed (landing page minimum).
- [ ] All placeholder text is replaceable (no hard-coded personal info).
- [ ] Images are either included with rights or clearly marked as placeholders.
- [ ] Dark text on light backgrounds, or light text on dark backgrounds — no
  low-contrast sections.

### Responsive behaviour

- [ ] Desktop layout is polished and complete.
- [ ] Tablet layout is intentional (not just a squished desktop).
- [ ] Mobile layout is fully usable — navigation works, text is readable,
  CTAs are tappable.
- [ ] No horizontal overflow on any breakpoint.

### Content & messaging

- [ ] `description` in `framer.json` is compelling and under 300 characters.
- [ ] README includes at least one preview image.
- [ ] README lists key features (5–10 bullet points).
- [ ] Tags in `framer.json` are accurate — they determine search visibility.
- [ ] Category is set correctly.

### Technical

- [ ] Template loads in Framer without errors.
- [ ] All Code Overrides (if any) function correctly.
- [ ] CMS collections (if any) have sample data.
- [ ] Forms (if any) have a configured submit action or clear "connect your
  form" instructions.
- [ ] SEO settings (page title, description) are filled.
- [ ] Favicon is set.

### Framer policies

- [ ] Template does not use Framer's branding or imply Framer endorsement.
- [ ] Template does not contain offensive, misleading, or illegal content.
- [ ] Any third-party assets (fonts, images, icons) are properly licensed for
  redistribution.
- [ ] Template does not bundle competitor products or promote external
  services in a way that violates Marketplace terms.

---

## Final sign-off

Before submitting, a second person (or a thorough self-review after 24 hours)
should:

1. [ ] Import the template / component into a fresh Framer project.
2. [ ] Customise every Property Control — does each one work as expected?
3. [ ] Resize the browser through all three breakpoints.
4. [ ] Run Lighthouse (Performance, Accessibility, Best Practices, SEO) —
   all scores ≥ 90.
5. [ ] Read the description and README as if seeing them for the first time.
   Are they clear? Do they sell the value?

---

**Status:** This checklist is a living document. If Framer updates their
acceptance criteria, update this file and propagate the changes to all active
templates.
