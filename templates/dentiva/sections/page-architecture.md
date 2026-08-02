# Page Architecture — Dentiva

Framer-native structural specification for every page and section in the
Dentiva template. Each entry describes purpose, content hierarchy, layout at
every breakpoint, spacing, interactions, and CMS connections.

---

## Global components

### Navbar

**Purpose:** Primary navigation and brand presence. Persistent across all
pages.

**Framer structure:**
```
Frame (Navbar Wrapper — full width, height 64px, bg neutral-0)
└── Frame (Navbar Container — max-width content-wide, centered)
    ├── Frame (Logo — SVG or Text, links to /)
    ├── Stack (Nav Links — horizontal, gap space-6)
    │   ├── Text (Home, Treatments, Doctors, About, Pricing, Journal)
    │   └── Text (Contact)
    └── Frame (CTA Button — primary, compact height 40px)
```

**Desktop:** Horizontal row: logo left, nav links centre-right, CTA right.

**Tablet:** Horizontal row. Logo left. Nav links collapse into a hamburger
menu (icon 44×44px, right-aligned). CTA may hide or move into the mobile menu.

**Mobile:** Same as tablet. Hamburger menu opens a full-width dropdown panel
below the navbar. Links stack vertically with `space-5` gap. CTA is
full-width at the bottom of the dropdown.

**Interactions:**
- Navbar background adds `shadow-sm` when the page scrolls past 20px
  (Framer scroll variant or Scroll Section trigger).
- Active page link changes colour to `brand-500` and adds a 2px bottom
  border in the same colour.
- Mobile menu toggles with a slide-down animation (250ms ease-out).

**Accessibility:**
- Navbar is a `<nav>` landmark (use Framer's Accessibility panel to set the
  role).
- Hamburger has `aria-label="Open menu"` / `aria-label="Close menu"`.
- Menu items are keyboard-focusable in order.
- Escape key closes the mobile menu.

---

### Footer

**Purpose:** Secondary navigation, contact information, and legal links.
Persistent across all pages.

**Framer structure:**
```
Frame (Footer Wrapper — full width, bg brand-50)
├── Stack (Footer Grid — horizontal, wrap, gap space-8)
│   ├── Stack (Clinic Info — vertical, gap space-3)
│   ├── Stack (Treatments Links — vertical, gap space-2)
│   ├── Stack (Clinic Links — vertical, gap space-2)
│   ├── Stack (Resources Links — vertical, gap space-2)
│   └── Stack (Contact & CTA — vertical, gap space-3)
└── Frame (Bottom Bar — border-top, padding space-4 vertical)
    ├── Text (Copyright)
    └── Stack (Legal Links — horizontal, gap space-4)
```

**Desktop:** 5 columns in a single row. Bottom bar: copyright left, legal
links right.

**Tablet:** 3 columns (columns 1–2 in row 1, columns 3–4 in row 2, column 5
in row 3 or full-width). Bottom bar stacks vertically, centred text.

**Mobile:** All columns stack vertically. Bottom bar text centred. Legal
links stack or wrap.

**CMS:** No CMS — static content. Buyer edits footer content directly.

---

### Appointment CTA Banner

**Purpose:** Conversion prompt placed after key sections. Appears on Home
(bottom), Treatments index, About, and Journal pages.

**Framer structure:**
```
Frame (CTA Banner — bg brand-50, radius-lg, padding space-12)
├── Stack (vertical, centred, gap space-5, max-width 600px)
│   ├── Text (Eyebrow)
│   ├── Text (Heading — h2)
│   ├── Text (Supporting — body-lg)
│   └── Stack (Buttons — horizontal, centred, gap space-4)
│       ├── Button (Primary)
│       └── Button (Secondary)
```

**Desktop:** Centred content block, max-width 600px, background colour fill.
**Tablet:** Same, narrower padding (space-8).
**Mobile:** Full-width, padding space-6. Buttons stack vertically, both
full-width.

**Component:** This is a Framer Component. Every instance uses the same
component with the same text and links. If the buyer changes the CTA, they
change it once.

---

### Section Wrapper

**Purpose:** Consistent horizontal padding and max-width for all page
sections.

**Framer structure:**
```
Frame (Section Wrapper — full width, padding: space-16 top, horizontal auto)
└── Frame (Content Container — max-width content-standard, centred)
```

**Variants:**
- `content-standard` (960px) — default for most sections
- `content-wide` (1160px) — for card grids
- `content-narrow` (720px) — for text-heavy sections (treatment descriptions,
  journal articles)

**Padding override per breakpoint:**
| Breakpoint | Horizontal padding | Top/bottom padding |
|-----------|-------------------|-------------------|
| Desktop | 32px | space-16 (64px) |
| Tablet | 24px | space-12 (48px) |
| Mobile | 16px | space-10 (40px) |

---

## Home page

### Section 1: Announcement Bar

**Purpose:** Brief promotional or informational message. Optional — can be
hidden by the buyer.

**Framer structure:**
```
Frame (Announcement Bar — full width, bg brand-500, height 40px)
└── Stack (horizontal, centred, gap space-2)
    ├── Text (Announcement text — white, text-label)
    └── Text (Link — white, underlined, "Book an appointment")
```

**Desktop/Tablet/Mobile:** Single line of centred text with inline link. On
mobile, text may wrap to two lines.

**Interaction:** Dismissible (close icon, 20×20px, white, right-aligned).
Dismissal stores a cookie/local storage flag so the bar stays hidden on
subsequent page loads.

---

### Section 2: Navbar

*(See Global Components — Navbar)*

---

### Section 3: Hero

**Purpose:** Primary landing impression. Communicates the clinic's value
proposition and provides the main conversion path.

**Framer structure:**
```
Frame (Hero Section — full width, min-height: 90vh)
├── Frame (Background Image — image fill, absolute, opacity may be dimmed
│   slightly with a dark overlay at 10% if needed for text contrast)
└── Stack (Hero Content — relative, vertical, left-aligned, max-width 640px,
    gap space-6, padding-left matches section wrapper)
    ├── Text (Eyebrow — text-label, brand-500 or white)
    ├── Text (Headline — display, neutral-900 or white depending on image)
    ├── Text (Supporting — lead, neutral-600 or white)
    └── Stack (Buttons — horizontal, gap space-4)
        ├── Button (Primary)
        └── Button (Secondary)
```

**Desktop (1200px+):**
- Content left-aligned, text occupies approximately 50–60% of the width.
- Image fills the right portion or acts as a full-bleed background.
- Two buttons side by side: primary + secondary.
- Vertical padding: generous (space-20 = 80px top and bottom).

**Tablet (810px–1199px):**
- Content remains left-aligned but narrower padding.
- Headline scales down (display → h1).
- Two buttons still side by side if space permits, or stack if the text is
  long.
- Min-height reduces to roughly 70vh.

**Mobile (0–809px):**
- Content fills the width, left-aligned.
- Headline scales down further (h1 → h2 size).
- Buttons stack vertically, both full-width.
- If the background image is complex, consider replacing it with a simpler
  image or a solid brand surface to preserve text readability.
- Min-height: auto (content dictates height). Padding: space-10 top and
  bottom.

**Typography overrides:**
| Element | Desktop | Tablet | Mobile |
|---------|---------|--------|--------|
| Headline | display (56px/64px) | h1 (40px/48px) | h2 size (28px/36px) |
| Supporting | lead (20px/32px) | lead (18px/28px) | body-lg (17px/26px) |

**Interaction:** Subtle fade-in on page load (200ms, no translation). No
auto-playing video.

**Accessibility:** If the hero image contains text, that text must also
appear in the HTML. If the image is decorative, mark it as such. Check text
contrast against the image — add a subtle dark overlay (10–20% opacity) if
needed.

**Component strategy:** The hero section itself is not a Framer Component
(only used once). But the CTA button pair is a Component instance.

---

### Section 4: Trust Strip

**Purpose:** Quick credibility signals immediately below the hero.

**Framer structure:**
```
Frame (Trust Strip — full width, bg neutral-0 or neutral-25)
└── Stack (horizontal, centred, gap space-10, wrap)
    └── 4 × Stack (Icon + Text pair — horizontal, gap space-2)
        ├── Frame (Icon — 24px, brand-400)
        └── Text (text-label, neutral-700)
```

**Desktop:** 4 items in a single horizontal row, evenly distributed.

**Tablet:** 2 rows × 2 columns. Centred.

**Mobile:** Single column, 4 stacked items. Centred text with icon above
text.

**Padding:** space-6 top and bottom. Not a large section — a quick visual
beat.

---

### Section 5: Treatments Grid

**Purpose:** Overview of available services. Links to individual Treatment
Detail pages.

**Framer structure:**
```
Frame (Section Wrapper — content-wide)
├── Stack (Section Header — vertical, centred, gap space-2)
│   ├── Text (Eyebrow)
│   ├── Text (Heading — h2)
│   └── Text (Intro — body-lg, max-width 600px, centred)
└── Grid (3 columns desktop, 2 tablet, 1 mobile, gap space-6 / space-8)
    └── 6 × CMS Treatment Card instances
```

**Treatment Card (Framer Component):**
```
Frame (Card — bg neutral-0, radius-lg, shadow-sm, padding space-6)
└── Stack (vertical, gap space-4)
    ├── Frame (Icon — 32px, brand-500)
    ├── Text (Title — h4)
    ├── Text (Description — body, neutral-600, 2–3 lines)
    └── Text (Link — "Learn more →", text-label, brand-500)
```

**CMS connection:** Each card is connected to a CMS item from the Treatments
collection. The card displays: icon, name, short description. Links to
`/treatments/[slug]`.

**Interaction:** Card hover: shadow-sm → shadow-md, slight scale (1.01).
Clicking anywhere on the card navigates to the treatment detail page. The
"Learn more" link has a visible focus state.

**Responsive:** Grid collapses: 3 → 2 → 1 column as breakpoints decrease.

**"View all treatments" link** below the grid, centred. Text link or
secondary button.

---

### Section 6: Clinic Philosophy

**Purpose:** Build trust by articulating values and approach.

**Framer structure:**
```
Frame (Section Wrapper — content-standard, bg neutral-25)
├── Stack (Section Header — centred, gap space-2)
│   ├── Text (Eyebrow)
│   └── Text (Heading — h2)
└── Grid or Stack (3 columns, gap space-8)
    └── 3 × Philosophy item:
        Stack (vertical, gap space-3)
        ├── Frame (Icon — 32px, brand-500)
        ├── Text (Heading — h4, neutral-900)
        └── Text (Body — body, neutral-600)
```

**Desktop:** 3 equal columns.

**Tablet:** 3 columns (if space permits) or 2+1 stacked.

**Mobile:** Single column, all items stacked.

**Background:** Use `neutral-25` to visually separate this section from the
treatments grid above it. Alternating section backgrounds (white → warm
surface → white) creates rhythm.

---

### Section 7: Treatment Process

**Purpose:** Demystify the patient journey. Reduce anxiety by showing what
happens.

**Framer structure:**
```
Frame (Section Wrapper — content-standard, bg neutral-0)
├── Stack (Section Header — centred)
│   ├── Text (Eyebrow)
│   └── Text (Heading — h2)
└── Stack (horizontal, gap space-6, wrap on tablet/mobile)
    └── 4 × Process Step:
        Stack (vertical, gap space-3)
        ├── Text (Step number — display/h1, brand-200, decorative)
        ├── Text (Heading — h4, neutral-900)
        └── Text (Body — body, neutral-600)
```

**Desktop:** 4 steps in a horizontal row. Number is large and decorative
behind or above the heading.

**Tablet:** 2×2 grid.

**Mobile:** Single column, 4 stacked steps.

**Interaction:** None beyond scroll reveal. Steps can have a subtle connecting
line between them on desktop (a 1px line in `neutral-200` stretching from
the right edge of step N to the left edge of step N+1). This line hides on
tablet/mobile.

---

### Section 8: Featured Doctors

**Purpose:** Humanise the clinic. Show the people behind the care.

**Framer structure:**
```
Frame (Section Wrapper — content-wide, bg neutral-25)
├── Stack (Section Header — centred)
│   ├── Text (Eyebrow)
│   ├── Text (Heading — h2)
│   └── Text (Intro — body-lg, max-width 600px, centred)
├── Grid (3 columns desktop, 2 tablet, 1 mobile)
│   └── 3 × CMS Doctor Card instances
└── Text (Link — "Meet the whole team →", centred)
```

**Doctor Card (Framer Component):**
```
Frame (Card — bg transparent)
└── Stack (vertical, gap space-4)
    ├── Frame (Photo — aspect 3:4, radius-md, image fill)
    ├── Stack (vertical, gap space-1)
    │   ├── Text (Name — h3, neutral-900)
    │   ├── Text (Title — body, neutral-600)
    │   └── Text (Specialisation badge — text-label-sm, brand-500)
    └── Text (Short bio — body-sm, neutral-600, 3–4 lines)
```

**CMS connection:** Connected to the Doctors collection. Card displays:
photo, name, title, specialisation, and a short excerpt from the bio.

**Interaction:** Clickable card → navigates to `/doctors/[slug]`.

**Photo sizing:** At 3 columns on desktop, photos are roughly 350px wide ×
467px tall (3:4). Ensure CMS images are at least 700×933px (2×) for sharp
rendering.

---

### Section 9: Testimonials

**Purpose:** Social proof. Real patient experiences build confidence.

**Framer structure:**
```
Frame (Section Wrapper — content-standard, bg neutral-0)
├── Stack (Section Header — centred)
│   ├── Text (Eyebrow)
│   └── Text (Heading — h2)
└── Grid or Stack (wrap, 3 columns max, gap space-6)
    └── 3 × CMS Testimonial Card instances
```

**Testimonial Card (Framer Component):**
```
Frame (Card — bg neutral-25, radius-lg, padding space-8)
└── Stack (vertical, gap space-5)
    ├── Frame (Opening quote icon — decorative, brand-200)
    ├── Text (Quote — body-lg, neutral-800, italic or regular)
    ├── Frame (Stars — 5 icons, 16px, brand-500)
    └── Stack (Attribution — horizontal, gap space-3)
        ├── Frame (Optional photo — 1:1, radius-full, 48px)
        └── Stack (vertical, gap space-0)
            ├── Text (Name — text-label, neutral-900)
            └── Text (Treatment — body-sm, neutral-600)
```

**CMS connection:** Connected to the Testimonials collection.

**Desktop:** 3 cards in a row.

**Tablet:** 2 cards in a row (third card wraps to a second row, centred).

**Mobile:** 1 card per row, full-width.

**Testimonial content note:** All testimonial text, names, and ratings are
demonstration content and must be replaced with genuine patient testimonials
before publishing.

---

### Section 10: Payment and Insurance

**Purpose:** Reduce a major conversion barrier — cost uncertainty.

**Framer structure:**
```
Frame (Section Wrapper — content-standard, bg neutral-25)
├── Stack (Section Header — centred)
│   ├── Text (Eyebrow)
│   └── Text (Heading — h2)
└── Stack (horizontal, gap space-10, wrap on mobile)
    ├── Stack (Insurance — vertical, gap space-4, flex 1)
    │   ├── Text (Subheading — h3)
    │   ├── Text (Body — body, neutral-600)
    │   └── Grid (Insurance logos — 2 or 3 columns, small text labels)
    └── Stack (Payment — vertical, gap space-4, flex 1)
        ├── Text (Subheading — h3)
        ├── Text (Body — body, neutral-600)
        └── Stack (Payment options list — vertical, gap space-2)
```

**Desktop:** 2 columns (insurance left, payment right).

**Tablet:** 2 columns, narrower gap.

**Mobile:** Single column, stacked. Insurance first, payment second.

**Call to action below:** "View pricing guide →" link or secondary button,
centred.

---

### Section 11: FAQ

**Purpose:** Answer common questions. Reduce pre-consultation anxiety.
Improve SEO with structured Q&A content.

**Framer structure:**
```
Frame (Section Wrapper — content-narrow, bg neutral-0)
├── Stack (Section Header — centred)
│   ├── Text (Eyebrow)
│   └── Text (Heading — h2)
└── Stack (vertical, gap space-0)
    └── 6–8 × Accordion Items
```

**Accordion Item (Framer Component):**
```
Frame (Accordion — full width)
├── Frame (Header — padding space-5 vertical, clickable, border-bottom)
│   ├── Text (Question — body-lg, neutral-800)
│   └── Frame (Icon — 20px, brand-500, rotates on open)
└── Frame (Body — padding space-5 bottom, collapsible)
    └── Text (Answer — body, neutral-600)
```

**Interaction:**
- Clicking a header toggles that accordion open/closed.
- Opening one accordion does not close others (multiple can be open).
- Icon rotates 45° (plus → ×) or 180° (chevron) on open.
- Transition: 250ms ease-out for height change.

**Content:** See `copy/site-copy.md` for FAQ content.

---

### Section 12: Appointment CTA Banner

*(See Global Components — Appointment CTA Banner)*

---

### Section 13: Footer

*(See Global Components — Footer)*

---

## Treatments index page

### Hero

Same structural pattern as Home hero but smaller: min-height 40–50vh,
narrower text column, no secondary CTA (just "Browse treatments" anchor link
or scroll).

### Treatment grid

**Framer structure:**
```
Frame (Section Wrapper — content-wide)
├── Stack (Filter Pills — horizontal, centred, gap space-2, wrap)
│   └── N × Text (Pill — text-label-sm, padding 8px 16px, radius-full,
│       brand-50 bg or brand-500 bg for active)
└── Grid (Treatment Cards — 3/2/1 columns)
    └── CMS-connected treatment cards
```

**Filter interaction (simplified Framer approach):**
Rather than building a dynamic filter, use Framer's CMS filtering to create
separate CMS lists for each category, then show/hide them with a tab
component. This is a Framer-native approach that avoids custom JavaScript.

Alternative simpler approach: no filtering — just a full grid with category
badges on each card. Scroll to browse.

---

## Treatment Detail page

### Hero

Narrower than Home hero. Image on the right (or top on mobile), text on the
left.

**Framer structure:**
```
Frame (Hero — content-wide)
└── Stack (horizontal → vertical on mobile, gap space-10)
    ├── Stack (Text — vertical, flex 1, gap space-4)
    │   ├── Text (Category badge — text-label-sm)
    │   ├── Text (Treatment name — h1)
    │   └── Text (Short description — lead)
    └── Frame (Hero image — radius-lg, aspect 16:9 or 4:3)
```

### Content sections

**Framer structure:**
```
Frame (Section Wrapper — content-narrow)
└── Stack (vertical, gap space-12)
    ├── Content block: Heading (h2) + Body text
    ├── Content block: Heading + Body
    ├── Content block: Heading + Numbered list
    ├── Content block: Heading + Body
    ├── Pricing table (simple rows, not an HTML table —
    │   use Stacks within Stacks)
    ├── FAQ Accordions
    └── Related treatments (3 treatment cards, same component)
```

Each content block is a Stack with a heading and body text. This keeps the
CMS flexible — the buyer can reorder blocks without restructuring.

**CMS connection:** The treatment detail page is a CMS-driven page. Content
blocks can be implemented as rich text fields (for maximum buyer flexibility)
or as structured fields (for consistent rendering). The recommended approach
is structured fields for key information (duration, recovery, price range)
and rich text for the main description.

**Sidebar (desktop only):**
On desktop, a sticky sidebar can display:
- Treatment duration
- Recovery time
- Price range
- "Book a consultation" CTA button
- Related treatments links

On tablet and mobile, this information moves inline — either between content
sections or at the top (below the hero) as a horizontal summary strip.

---

## Doctors index page

Same structural pattern as the Treatments index. Hero → Grid of doctor cards.

**Doctor card interaction:** Clicking navigates to `/doctors/[slug]`.

---

## Doctor Detail page

**Framer structure:**
```
Frame (Section Wrapper — content-standard)
└── Stack (horizontal → vertical on mobile, gap space-10)
    ├── Frame (Photo column — flex 0.35)
    │   ├── Frame (Photo — aspect 3:4, radius-lg, image fill)
    │   └── Stack (Quick info — vertical, gap space-1, margin-top space-4)
    │       ├── Text (Languages — body-sm)
    │       └── Text (Registration — body-sm, neutral-400,
    │           "GDC: 123456 — demonstration")
    └── Stack (Content column — flex 0.65, vertical, gap space-8)
        ├── Stack (Name block — vertical, gap space-1)
        │   ├── Text (Name — h1)
        │   ├── Text (Title — lead, neutral-600)
        │   └── Text (Specialisation badge)
        ├── Stack (Bio — vertical, gap space-4)
        │   ├── Text (Heading — h3, "About")
        │   └── Text (Bio paragraphs — body-lg)
        ├── Stack (Education — vertical, gap space-3)
        │   ├── Text (Heading — h3, "Education & Training")
        │   └── Text (List — body)
        ├── Stack (Memberships — vertical, gap space-3)
        │   ├── Text (Heading — h3, "Professional Memberships")
        │   └── Text (List — body)
        └── Button (Primary — "Book with Dr. [Name]")
```

**Desktop:** Two columns — photo left (35%), content right (65%).
**Tablet:** Two columns (40/60 split) or stack to single column if photo
column feels too narrow.
**Mobile:** Single column. Photo full-width (or constrained to 75%), content
below.

**CMS connection:** CMS-driven page from the Doctors collection.

---

## About page

**Framer structure:**
```
Page
├── Section: Hero (same pattern as Treatments hero)
├── Section: Our Story (content-narrow, text-only or text + image)
├── Section: Our Values (3 columns, icon + heading + text)
├── Section: The Clinic (image gallery or single large image + caption)
├── Section: Community (content-narrow, text + optional image)
└── Section: Appointment CTA Banner
```

**Values section:** Same structural pattern as Clinic Philosophy on Home
(page-architecture.md#section-6). Reuse the same Framer Component if
possible — just change the content.

**Clinic gallery:** A horizontal Stack or Grid of 3–4 images with
`radius-md`. On mobile, images stack or become a horizontally scrollable
strip.

---

## Pricing page

**Framer structure:**
```
Page
├── Section: Hero (narrower — content-standard)
├── Section: Disclaimer (content-narrow, warning-100 bg, warning-500 text,
│   border-radius-md, padding-space-6)
├── Section: Pricing tables
│   └── Stack (vertical, gap space-12)
│       └── Per category:
│           ├── Text (Category heading — h3)
│           └── Stack (Pricing rows — vertical, gap space-0)
│               └── Per row: Stack (horizontal, space-between,
│                   padding space-3 vertical, border-bottom light)
│                   ├── Text (Treatment name — body)
│                   └── Text (Price range — body, neutral-600)
├── Section: Payment & Insurance (same component as Home section 10)
└── Section: Appointment CTA Banner
```

**Pricing row design:** Simple, text-only rows with a subtle border between
items. No heavy table borders. This is a pricing guide, not an invoice — keep
it visually light.

**Category organisation:** Use expandable sections (accordions) or visible
sections with headings. Expandable keeps the page shorter; visible is easier
to scan. Recommended: visible sections with sticky or in-page category nav
links at the top.

---

## Journal index page

**Framer structure:**
```
Page
├── Section: Hero (narrower)
├── Section: Filter/Category tabs (optional)
├── Section: CMS Journal Cards Grid (3/2/1 columns)
└── Section: Newsletter sign-up (optional)
```

**Journal Card:** Same component pattern as treatment cards, adapted for
editorial content. Image (16:9), category badge, title, excerpt, date.

**CMS connection:** Connected to Journal Posts collection.

---

## Contact page

**Framer structure:**
```
Page
├── Section: Hero (narrower)
└── Section: Contact Content
    └── Stack (horizontal → vertical on mobile, gap space-10)
        ├── Stack (Form — flex 0.55, vertical, gap space-5)
        │   ├── Text (Heading — h2, "Send us a message")
        │   └── Form fields (see below)
        └── Stack (Clinic Info — flex 0.45, vertical, gap space-8)
            ├── Stack (Address — vertical, gap space-2)
            ├── Stack (Hours — vertical, gap space-2)
            ├── Stack (Emergency — vertical, gap space-2)
            └── Frame (Map placeholder)
```

**Form fields (Framer Form component):**
Each field is a Framer form input with a label and validation.

```
Form
├── Text Input (Name — required)
├── Email Input (Email — required)
├── Tel Input (Phone — optional)
├── Select (Reason — required)
│   Options: New appointment, Reschedule, Treatment question,
│   Billing question, Other
├── Text Input (Preferred days — optional)
├── Textarea (Message — required, min 10 characters)
├── Select (Heard about us — optional)
│   Options: Search engine, Recommendation, Social media,
│   Insurance provider, Other
└── Submit Button (Primary — "Send message")
```

**Form validation:** Use Framer's built-in form validation. Required fields
must show an error state if submitted empty. Email must validate format.
Message must be at least 10 characters.

**Success state:** After successful submission, the form is replaced by the
success message (see `copy/site-copy.md`). Implement using Framer's form
submit action — either a simple success redirect or a conditional visibility
swap.

**Mobile:** Stack the two columns vertically. Form first, clinic info below
it. Full-width form fields.

---

## Legal / Privacy page

**Framer structure:**
```
Page
└── Section (content-narrow, padding space-16 top and bottom)
    └── Stack (vertical, gap space-10)
        ├── Text (h1 — "Privacy Policy" or "Legal Information")
        ├── Stack (Privacy content — vertical, gap space-5)
        │   └── Multiple Text blocks (headings + body)
        ├── Divider (border-light)
        ├── Stack (Terms content — vertical, gap space-5)
        └── ...
```

Simple, text-only page. Use rich text or multiple text layers. No special
interactions.

---

## 404 page

**Framer structure:**
```
Page
└── Frame (full viewport height, centred content)
    └── Stack (vertical, centred, gap space-6, max-width 480px)
        ├── Text (h1 — "Page not found")
        ├── Text (body — explanation)
        ├── Button (Primary — "Back to home")
        └── Text (Link — "Visit our Treatments page")
```

---

## Cookie consent banner

**Framer structure:**
```
Frame (Fixed bottom, full width, bg neutral-900, text white)
└── Stack (horizontal, centred, gap space-6, padding space-4)
    ├── Text (body-sm — cookie message)
    └── Stack (Buttons — horizontal, gap space-3)
        ├── Text (Link — "Manage preferences", white/underline)
        └── Button (Primary — "Accept all", compact)
```

**Interaction:** Banner is hidden by default. A cookie check (local storage)
determines whether to show it. "Accept all" sets the flag and hides the
banner. "Manage preferences" scrolls to the cookie section of the Privacy
Policy.

In Framer, this can be implemented using a combination of a Component with
variants (visible/hidden) and a simple interaction or a code override for
the cookie logic.

---

## Responsive breakpoint summary

| Breakpoint | Min width | Layout behaviour |
|-----------|-----------|-----------------|
| Desktop | 1200px | Full multi-column layouts, horizontal stacks, 3-column grids |
| Tablet | 810px | Reduced columns (3→2), some horizontal stacks flip to vertical, spacing scales down |
| Mobile | 390px | Single-column throughout, all stacks vertical, full-width buttons, reduced type scale, compact spacing |

### Key responsive rules

1. **Grid columns:** 3 (desktop) → 2 (tablet) → 1 (mobile).
2. **Horizontal Stacks (text+image):** Flip to vertical on tablet and below.
3. **Navigation:** Horizontal links → hamburger menu on tablet and below.
4. **Buttons:** Side by side on desktop → stacked full-width on mobile.
5. **Section spacing:** Reduce `space-16` → `space-12` → `space-10` for
   vertical section padding.
6. **Content width:** Content containers use `padding: 0 32px` (desktop),
   `0 24px` (tablet), `0 16px` (mobile) — set as a Framer breakpoint
   override on the section wrapper component.
7. **Type scale:** Headings reduce by approximately 15–20% at tablet and
   an additional 15–20% at mobile. See design system for exact values.

---

## Reusable Framer Components — summary

These should be created as Framer Components so they stay synchronised
across pages:

| Component | Variants (if any) | States |
|-----------|-------------------|--------|
| Navbar | Desktop / Mobile menu open | Scroll shadow |
| Footer | — | — |
| Section Wrapper | Narrow / Standard / Wide | — |
| Appointment CTA Banner | — | — |
| Primary Button | Size: Default / Compact / Full-width | Default, Hover, Pressed, Focus, Disabled |
| Secondary Button | Size: Default / Compact / Full-width | Default, Hover, Pressed, Focus, Disabled |
| Treatment Card | — | Default, Hover |
| Doctor Card | — | Default, Hover |
| Testimonial Card | — | — |
| Journal Card | — | Default, Hover |
| Accordion Item | Open / Closed | — |
| Form Field (grouped) | Text / Email / Tel / Select / Textarea | Default, Focus, Error, Disabled |
| Badge | Default / Brand / Success / Warning | — |
| Filter Pill | Active / Inactive | Hover |
| Cookie Banner | Visible / Hidden | — |

Each component should have its own page in the Framer project (in a
`_components` folder or similar) so the buyer can find and edit them easily.
