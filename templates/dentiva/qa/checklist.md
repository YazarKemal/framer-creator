# QA Checklist — Dentiva

A comprehensive quality-assurance checklist specific to the Dentiva dental
clinic Framer template. Every item must be confirmed before the template is
submitted to the Framer Marketplace.

Use Markdown checkboxes to track progress:
- `[ ]` Not yet checked
- `[x]` Passed
- `[~]` Needs attention (add a note)
- `[n/a]` Not applicable

---

## 1. Content quality

- [ ] All page copy is free of spelling and grammar errors
- [ ] All page copy is in English and at approximately a Grade 8 reading level
- [ ] Dental terms are defined on first use
- [ ] No lorem ipsum or placeholder gibberish remains anywhere
- [ ] No exaggerated or superlative claims ("best", "leading", "revolutionary")
- [ ] No guaranteed clinical promises ("pain-free", "permanent results",
  "100% success")
- [ ] All clinician names, credentials, and registration numbers are clearly
  fictional demonstration content
- [ ] All testimonials are clearly labelled as demonstration content
- [ ] All prices are clearly labelled as demonstration figures
- [ ] Clinic address, phone number, and email are clearly demonstration content
- [ ] No fake awards, certifications, or association memberships presented as
  real
- [ ] No unsupported statistics or percentages claimed as factual
- [ ] Tone is consistent across all pages — professional, warm, calm, clear
- [ ] No urgency or fear-based language ("book now before it's too late",
  "don't risk your health")
- [ ] Cookie notice and privacy policy copy present and coherent
- [ ] 404 page copy is helpful and on-brand

---

## 2. Medical-claim safety

- [ ] No page implies that the template itself provides medical advice
- [ ] No diagnostic questionnaires or self-assessment tools that suggest a
  diagnosis
- [ ] No before-and-after galleries making unsubstantiated claims
- [ ] Treatment descriptions use factual, educational language — not marketing
  promises
- [ ] All treatment content is structured as information, not recommendation
- [ ] Disclaimer text is present on the pricing page
- [ ] Privacy policy demonstration text covers patient data handling
  (GDPR-style)
- [ ] No content that could be interpreted as guaranteeing treatment outcomes

---

## 3. Typography

- [ ] Crimson Pro and Inter fonts load correctly on all pages
- [ ] Font fallback stacks are visible during font loading (no flash of
  invisible text)
- [ ] Heading hierarchy is logical: single `<h1>` per page, heading levels
  do not skip
- [ ] Desktop type scale matches the design system
- [ ] Tablet type scale matches the design system
- [ ] Mobile type scale matches the design system
- [ ] No text smaller than 11px on any breakpoint
- [ ] Line height (leading) is comfortable — no cramped or floating text
- [ ] Text contrast meets WCAG AA on all backgrounds
- [ ] Link text is visually distinguishable from body text (colour +
  underline on hover)

---

## 4. Spacing

- [ ] Section vertical spacing uses design-system tokens consistently
- [ ] Section horizontal padding is consistent across pages
- [ ] Content widths (narrow, standard, wide) are applied correctly
- [ ] Card internal padding is consistent across all card types
- [ ] Gap between cards is consistent in grids
- [ ] No unwanted large gaps or collapsed margins
- [ ] No content touches the edge of the viewport on mobile (minimum 16px
  padding)
- [ ] Stack and Grid gap values use the spacing scale (not arbitrary numbers)

---

## 5. Responsive behaviour

### Desktop (1440px reference)

- [ ] No horizontal scroll bar appears
- [ ] All content is within the intended content width
- [ ] Multi-column layouts render correctly
- [ ] Images are not stretched or distorted
- [ ] Navbar is horizontal with all links visible
- [ ] Footer renders in 5 columns
- [ ] Card grids render in 3 columns where specified

### Tablet (810px reference)

- [ ] No horizontal scroll bar appears
- [ ] Grid columns reduce correctly (3→2)
- [ ] Horizontal stacks that should flip to vertical do so
- [ ] Navbar switches to hamburger menu
- [ ] Type scale reduces as specified
- [ ] Section spacing reduces as specified
- [ ] Images remain within their containers
- [ ] No overlapping elements

### Mobile (390px reference)

- [ ] No horizontal scroll bar appears (most critical)
- [ ] All grids reduce to 1 column
- [ ] All stacks are vertical
- [ ] Buttons are full-width where specified
- [ ] Touch targets are at least 44×44px
- [ ] Form fields are full-width and usable
- [ ] Mobile menu opens, scrolls, and closes correctly
- [ ] Text is readable without zooming
- [ ] No content is permanently hidden without an alternative
- [ ] Sticky mobile CTA (if implemented) does not obscure content

### Cross-breakpoint

- [ ] Transition between breakpoints is smooth — no content jumps or
  disappears
- [ ] Images scale within their containers at all widths
- [ ] Background colours and images cover their containers fully

---

## 6. Component consistency

- [ ] All instances of a Framer Component render identically
- [ ] Component overrides (if any) do not break the component layout
- [ ] Navbar is identical on every page
- [ ] Footer is identical on every page
- [ ] CTA Banner component is identical wherever used
- [ ] Treatment Cards are identical on Treatments index and Home page
- [ ] Doctor Cards are identical on Doctors index and Home page
- [ ] Testimonial Cards are identical wherever used
- [ ] Accordion items behave identically wherever used
- [ ] Button variants (primary, secondary, sizes) render consistently
- [ ] Form fields have consistent styling across all forms

---

## 7. CMS collections

### Treatments collection

- [ ] Collection is created with all fields from the spec
- [ ] At least 6 sample treatment entries are populated
- [ ] Each entry has a unique slug
- [ ] Short descriptions fit within card layouts (no overflow)
- [ ] Categories are correctly assigned
- [ ] Images are properly sized and cropped
- [ ] Treatment Detail pages render for every treatment
- [ ] Related treatments link correctly

### Doctors collection

- [ ] Collection is created with all fields from the spec
- [ ] At least 3 sample doctor entries are populated
- [ ] Each entry has a unique slug
- [ ] Photos are properly sized (3:4 aspect ratio, min 700×933px)
- [ ] Doctor Detail pages render for every doctor
- [ ] "Book with Dr. [Name]" CTA is present on each detail page

### Journal Posts collection

- [ ] Collection is created with all fields from the spec
- [ ] At least 3 sample journal entries are populated
- [ ] Each entry has a unique slug and a featured image (16:9)
- [ ] Journal cards display correctly on the index page
- [ ] Category badges display correctly

### Testimonials collection

- [ ] Collection is created with all fields from the spec
- [ ] At least 3 sample testimonials are populated
- [ ] Ratings (1–5) display correctly as star icons
- [ ] Optional photos render correctly when present and don't break when absent
- [ ] Verified badge toggles correctly
- [ ] Testimonials render correctly on Home page and relevant Treatment
  Detail pages

### CMS general

- [ ] CMS lists handle empty states gracefully (no broken layouts if a
  collection is empty)
- [ ] CMS lists handle single-item collections (no grid stretching)
- [ ] CMS lists handle large collections (pagination or scroll — no
  performance issues with 50+ items)
- [ ] Rich text fields render correctly with all formatting

---

## 8. Forms

### Appointment / contact form

- [ ] All fields render with visible labels
- [ ] Required fields are visually marked (asterisk or "(required)" text)
- [ ] Email field validates email format
- [ ] Required fields show an error if submitted empty
- [ ] Message field enforces minimum character count (10 characters)
- [ ] Error messages are descriptive and helpful
- [ ] Error state styling is consistent (red border, error-coloured text)
- [ ] Form submission works — success state displays
- [ ] Success message replaces the form (or navigates to a success page)
- [ ] Form data is being collected (check Framer's form submissions panel)
- [ ] Tab order through form fields is logical
- [ ] Form labels are programmatically associated with their inputs
- [ ] Select/dropdown fields are keyboard-operable

### Newsletter sign-up (if implemented)

- [ ] Email field validates correctly
- [ ] Success state displays after submission
- [ ] Unsubscribe language is present or implied in surrounding copy

---

## 9. Navigation

- [ ] All internal links navigate to the correct page
- [ ] Navbar links highlight the current page (active state)
- [ ] Mobile menu opens and closes correctly
- [ ] Mobile menu links navigate correctly
- [ ] Mobile menu closes after tapping a link
- [ ] CTA buttons link to the correct destination (booking form or contact
  page)
- [ ] Footer links navigate correctly
- [ ] External links (social media, insurance providers) open appropriately
- [ ] No broken links or 404 errors
- [ ] "Back to home" link on 404 page works

---

## 10. Interactions

- [ ] Card hover states work (shadow increase, subtle scale)
- [ ] Button hover states work (colour transition)
- [ ] Button active/pressed states work
- [ ] Accordion open/close works smoothly
- [ ] Mobile menu toggle works smoothly
- [ ] Scroll-triggered section reveals work (if implemented)
- [ ] Navbar shadow appears on scroll and disappears at top
- [ ] Cookie banner dismiss works and persists across page loads
- [ ] All interactive elements have a visible focus state
- [ ] No elements flash or flicker during interactions
- [ ] Animations respect `prefers-reduced-motion` (test by enabling
  "Reduce motion" in OS settings)

---

## 11. Accessibility

### Colour and contrast

- [ ] All body text meets 4.5:1 contrast minimum (WCAG AA)
- [ ] All large text (18px+ bold or 24px+ regular) meets 3:1 minimum
- [ ] Links are distinguishable from body text by more than colour alone
- [ ] Form error states don't rely solely on colour (text + icon + border)
- [ ] Focus indicators are clearly visible on all interactive elements
- [ ] No information is conveyed by colour alone

### Keyboard navigation

- [ ] All interactive elements are reachable via Tab key
- [ ] Tab order follows the visual order of the page
- [ ] No keyboard traps — focus never gets stuck on an element
- [ ] Mobile menu can be opened and closed via keyboard
- [ ] Accordions can be toggled via keyboard (Enter or Space)
- [ ] Links and buttons are activated by Enter (and Space for buttons)
- [ ] Escape key closes modals, menus, and accordions (as appropriate)
- [ ] Form can be completed and submitted via keyboard alone

### Screen reader

- [ ] All content images have descriptive alt text
- [ ] Decorative images have empty alt attributes or are marked as decorative
- [ ] Form inputs have programmatically associated labels
- [ ] Navigation is wrapped in a `<nav>` landmark
- [ ] Main content is wrapped in a `<main>` landmark
- [ ] Footer is wrapped in a `<footer>` landmark (or `<contentinfo>`)
- [ ] Page has a single `<h1>` and a logical heading structure
- [ ] Icon-only buttons have accessible names (aria-label)
- [ ] Mobile menu toggle announces its state (expanded/collapsed)
- [ ] Form error messages are announced to screen readers
- [ ] Form success message is announced to screen readers

### Touch and pointer

- [ ] All touch targets are at least 44×44px on mobile
- [ ] No hover-dependent interactions without a tap/click equivalent
- [ ] No elements that require precise cursor positioning

---

## 12. Keyboard navigation (detailed)

- [ ] `Tab`: Moves focus forward through interactive elements in logical order
- [ ] `Shift + Tab`: Moves focus backward
- [ ] `Enter`: Activates links and buttons
- [ ] `Space`: Activates buttons and toggles checkboxes
- [ ] `Escape`: Closes mobile menu, closes accordion (if applicable)
- [ ] `Arrow keys`: Navigate within select dropdowns and radio groups
- [ ] Visible `:focus-visible` style on every focused element — no
  `outline: none` without a replacement

---

## 13. Focus states

- [ ] Focus ring is visible: 2px solid brand-500, offset 2px from element
- [ ] Focus ring is consistent across all interactive elements
- [ ] Focus ring has sufficient contrast against all backgrounds
- [ ] Focus ring does not clip or get hidden by overflow
- [ ] Focus order follows visual reading order (left to right, top to bottom)
- [ ] Focus returns to the trigger element after closing a modal or menu
- [ ] Hover state and focus state are visually distinct (both can be
  present simultaneously)

---

## 14. Image optimisation

- [ ] All images are in an appropriate format (PNG for graphics, JPG/WebP for
  photos)
- [ ] CMS images have recommended dimensions documented for the buyer
- [ ] Hero images are sized appropriately (max ~2500px wide, compressed)
- [ ] No image is loaded at full resolution and scaled to a tiny display size
  in the browser
- [ ] Images have explicit width and height attributes or aspect-ratio
  constraints to prevent layout shift
- [ ] Placeholder images are clearly identifiable as placeholders
- [ ] Photo licences: all demonstration images are either Creative Commons
  (CC0/CC BY), royalty-free, or clearly marked as placeholder content
- [ ] No images contain embedded text that isn't also in the HTML

---

## 15. SEO

- [ ] Every page has a unique `<title>` tag
- [ ] Every page has a unique meta description (under 160 characters)
- [ ] Home page title includes clinic name and primary keyword
- [ ] Treatment Detail pages have descriptive titles (treatment name +
  clinic name)
- [ ] Heading hierarchy is correct on every page
- [ ] All images have alt text
- [ ] Canonical URLs are set (if applicable)
- [ ] No `noindex` on pages that should be indexed
- [ ] robots.txt is not blocking important pages (if configurable)
- [ ] Structured data (if any) is valid — e.g. LocalBusiness, FAQ, Breadcrumbs
- [ ] URL slugs are descriptive and hyphenated (e.g. `/treatments/dental-implants`)

---

## 16. Open Graph and social sharing

- [ ] Every page has `og:title` set
- [ ] Every page has `og:description` set
- [ ] Every page has `og:image` set (1200×630px recommended)
- [ ] `og:type` is set appropriately (`website` for most pages, `article`
  for Journal)
- [ ] Twitter card meta tags are set (`summary_large_image` for content
  pages)
- [ ] Social share preview renders correctly (test with a tool like
  opengraph.xyz or similar)

---

## 17. Performance

- [ ] Lighthouse Performance score ≥ 90
- [ ] Lighthouse Accessibility score ≥ 95
- [ ] Lighthouse Best Practices score ≥ 90
- [ ] Lighthouse SEO score ≥ 90
- [ ] No render-blocking resources (or minimal)
- [ ] Fonts load efficiently (use `font-display: swap` via Framer's font
  settings)
- [ ] Images are appropriately compressed
- [ ] No large JavaScript bundles (Framer handles this, but verify no custom
  code bloats the bundle)
- [ ] Pages load in under 3 seconds on a simulated 4G connection
- [ ] No layout shift during page load (CLS ≤ 0.1)
- [ ] No excessive DOM size (Framer-managed, but flag if a page has
  unusually many layers)

---

## 18. Browser testing

- [ ] Chrome (latest) — full pass
- [ ] Safari (latest) — full pass
- [ ] Firefox (latest) — full pass
- [ ] Edge (latest) — full pass
- [ ] Safari iOS (latest) — full pass on iPhone and iPad
- [ ] Chrome Android (latest) — full pass
- [ ] Samsung Internet (latest) — cursory pass

---

## 19. Mobile testing

- [ ] iPhone SE (375px) — no horizontal scroll, readable text, tappable CTAs
- [ ] iPhone 14 / 15 (390px) — full layout review
- [ ] iPhone 14 Pro Max (428px) — full layout review
- [ ] iPad (810px portrait) — tablet layout review
- [ ] iPad Pro (1024px portrait) — tablet layout review
- [ ] Android phone (360px–412px) — spot-check
- [ ] Real device testing (at minimum one iOS and one Android device)
- [ ] Both portrait and landscape orientations tested

---

## 20. Framer remix usability

- [ ] Template imports into a fresh Framer project without errors
- [ ] All CMS collections import with sample data intact
- [ ] All Framer Components import and render correctly
- [ ] All Framer Variables import with correct default values
- [ ] All Text Styles and Colour Styles import correctly
- [ ] Forms retain their configuration
- [ ] Breakpoint layouts are preserved
- [ ] Changing brand colour variables updates the site consistently
- [ ] Changing font variables updates the site consistently
- [ ] Adding a new CMS item (e.g. a new doctor) renders correctly on
  connected pages
- [ ] Template does not depend on any paid Framer features
  (`requiresPaidPlan: false` — or set correctly if paid features are used)

---

## 21. Editable variables

- [ ] Brand colour variables are clearly named and organised
- [ ] Changing a brand colour updates all instances across the site
- [ ] Spacing variables are clearly named
- [ ] Typography variables control font families
- [ ] Text Styles are linked to typography and colour variables
- [ ] No hard-coded colour values in any component (all use variables or
  styles)
- [ ] No hard-coded spacing values (all use variables or reference the
  spacing scale)

---

## 22. Placeholder replacement

- [ ] A "Getting Started" guide or README is included with the template
  explaining what to replace
- [ ] All clinician names are clearly placeholder
- [ ] All prices are clearly placeholder
- [ ] All testimonials are clearly placeholder
- [ ] Clinic address, phone, email are clearly placeholder
- [ ] Map embed (if any) shows a generic location or is marked as
  placeholder
- [ ] Photos are clearly placeholder (or licensed for redistribution)
- [ ] Privacy policy and terms are clearly marked as template text requiring
  legal review

---

## 23. Licensing

- [ ] All fonts are open-source and licensed for commercial redistribution
  (Crimson Pro: OFL, Inter: OFL)
- [ ] All icons are open-source and licensed for commercial use
  (Phosphor Icons: MIT)
- [ ] All demonstration images are either CC0, royalty-free with appropriate
  licence, or clearly placeholder
- [ ] No unlicensed stock photography
- [ ] Template itself carries an appropriate licence for Marketplace
  distribution

---

## 24. Marketplace preview assets

- [ ] Primary preview image: 2400×1600px PNG, under 5 MB
- [ ] Thumbnail: 800×600px PNG, under 1 MB
- [ ] Preview images accurately represent the template — no misleading
  mockups
- [ ] Preview images show the template with placeholder content, not real
  clinic data
- [ ] At least 2 additional gallery screenshots (optional but recommended)
- [ ] Preview images have been checked on a retina/high-DPI screen

---

## 25. Final publishing review

- [ ] Template name "Dentiva" is used consistently (or buyer has renamed
  throughout)
- [ ] `framer.json` manifest is complete and valid
- [ ] Template category is correctly set
- [ ] Tags are accurate (e.g. "dental", "clinic", "healthcare", "medical",
  "appointment")
- [ ] Template description for Marketplace is written (150–300 characters,
  compelling, accurate)
- [ ] No Framer branding or implied Framer endorsement in the template
- [ ] No competitor product mentions or external service promotions
- [ ] All links are relative (no absolute URLs pointing to a demo domain)
- [ ] Template has been tested by someone other than the creator (fresh eyes)
- [ ] Final remix test: import into a clean Framer account, customise, and
  publish a test site
- [ ] Test site reviewed on a real phone and tablet

---

## Notes

- Items marked `[~]` must include a comment describing the issue and how to
  resolve it.
- This checklist should be run once before initial submission and again after
  any significant update.
- A dental professional should review all treatment content before
  publication — this is the buyer's responsibility, but the template should
  not contain anything that would fail a basic factual review.
