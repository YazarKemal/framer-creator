# Dentiva — Premium Dental Clinic Framer Template

A complete Framer Marketplace template for a premium, multi-specialty dental
clinic. Dentiva is designed to feel credible, calm, and modern — suitable for
established clinics, group practices, and dental brands that want to attract
patients through a trustworthy online presence.

---

## Project overview

Dentiva provides a ready-to-publish Framer website for a dental clinic. Every
page is assembled with native Framer components (Frames, Stacks, Grids, CMS
collections, Forms, and Breakpoints). The template ships with realistic
starter content, a complete design system, and a CMS-powered architecture that
lets clinic staff update treatments, doctor profiles, and journal articles
without touching the layout.

**This is a Framer template — not a standalone React app or website builder.**
Customers remix it inside the Framer editor, replace the placeholder content
with their own, and publish.

### What Dentiva includes

- 10 production-ready pages (Home, Treatments, Treatment Detail, Doctors,
  Doctor Detail, About, Pricing, Journal, Contact, Legal)
- 4 CMS collections (Treatments, Doctors, Journal Posts, Testimonials)
- A full design system with colour, typography, spacing, and component tokens
- Responsive layouts for desktop, tablet, and mobile
- An appointment booking form with validation states
- SEO metadata and Open Graph defaults for every page
- Accessible markup and keyboard-navigable interactions
- Realistic starter content — no lorem ipsum

---

## Target users

### Primary buyer personas

| Persona | Needs |
|---------|-------|
| **Practice owner / dentist** | Professional online presence, patient acquisition, credibility with referring colleagues |
| **Clinic manager** | Easy to update content, integrates with existing booking system, reduces admin calls |
| **Marketing agency (dental niche)** | White-label starting point for client projects, consistent design, CMS for non-technical clients |
| **Startup dental group** | Fast launch, premium look on a budget, room to grow with more locations and services |

### End-user personas (patients)

| Persona | Motivation |
|---------|-----------|
| **Preventive care seeker** | Routine check-ups, cleanings, oral health maintenance |
| **Restorative patient** | Fillings, crowns, implants — wants to understand the process and cost |
| **Cosmetic patient** | Whitening, veneers, smile makeovers — motivated by aesthetics and confidence |
| **Parent / family organiser** | Needs a clinic that treats children and adults, convenient appointment times |
| **International / travelling patient** | Researching treatment options abroad, needs clear pricing and process information |

---

## Business use cases

1. **Single-location clinic** — uses Dentiva as the clinic's primary website
   with location details, team profiles, and a booking form.
2. **Multi-location group** — remixes the template for each practice,
   swapping CMS content while keeping brand consistency.
3. **Specialist referral hub** — positions the clinic as a centre for
   implants, orthodontics, or cosmetic dentistry, attracting referring
   dentists.
4. **Treatment tourism** — targets international patients with transparent
   pricing, process timelines, and travel guidance.
5. **Startup dental brand** — launches a new clinic with a polished digital
   presence from day one.

---

## Value proposition

**For the clinic:** A professional, high-trust website that converts visitors
into booked appointments. CMS-powered pages keep content fresh without
developer involvement. The design system ensures visual consistency as the
site grows.

**For the Framer customer:** A premium template that requires no coding. Every
element is a native Framer component — customise colours, fonts, images, and
copy directly in the editor. Property controls and variables make
brand-level changes fast and safe.

**For patients:** A calm, informative experience that answers questions,
introduces clinicians, explains treatments in plain language, and makes
booking straightforward — without aggressive sales pressure.

---

## Proposed pages

| # | Page | Route | CMS | Purpose |
|---|------|-------|-----|---------|
| 1 | Home | `/` | Testimonials | Primary landing and conversion page |
| 2 | Treatments | `/treatments` | Treatments | Browse all services by category |
| 3 | Treatment Detail | `/treatments/[slug]` | Treatments | Deep-dive on one treatment |
| 4 | Doctors | `/doctors` | Doctors | Meet the clinical team |
| 5 | Doctor Detail | `/doctors/[slug]` | Doctors | Individual clinician profile |
| 6 | About | `/about` | — | Clinic story, philosophy, facility |
| 7 | Pricing | `/pricing` | — | Treatment price ranges and policies |
| 8 | Journal | `/journal` | Journal Posts | Oral health articles and clinic news |
| 9 | Contact | `/contact` | — | Location, hours, contact form, map |
| 10 | Legal | `/legal` | — | Privacy policy, terms, cookie notice |

---

## CMS strategy

Dentiva uses four Framer CMS collections. Each collection is designed so that
non-technical clinic staff can add, edit, and remove content safely.

### Collections

| Collection | Fields | Connected pages |
|-----------|--------|-----------------|
| **Treatments** | Name, slug, category, short description, full description, duration, recovery, price range, icon, hero image, gallery | Treatments index, Treatment Detail, Home (featured treatments) |
| **Doctors** | Full name, slug, title, specialisation, bio, education, photo, hero image, languages, registration number | Doctors index, Doctor Detail, Home (featured doctors) |
| **Journal Posts** | Title, slug, author, publish date, category, excerpt, featured image, body | Journal index, Home (latest articles) |
| **Testimonials** | Patient name, treatment, quote, rating (1–5), photo (optional), verified badge (boolean) | Home (testimonial section), relevant Treatment Detail pages |

### CMS design principles

- Every text field uses Framer's **plain text or rich text** types — avoid
  unstructured blocks for fields that need consistent rendering.
- **Slugs** are auto-generated but manually overridable.
- **Images** use Framer's image field with alt text support.
- **Optional fields** are clearly marked so the CMS UI doesn't feel cluttered
  with empty required fields.
- Reference fields (e.g. linking a testimonial to a treatment) use Framer's
  **Collection Reference** type where available.

---

## Framer-native implementation strategy

Dentiva is built entirely with Framer's built-in toolset. No custom React
components are required for the core template.

### Layout primitives

| Purpose | Framer component |
|---------|-----------------|
| Page sections | `Frame` with max-width and auto horizontal padding |
| Row layouts | `Stack` (horizontal) with gap and alignment |
| Column layouts | `Stack` (vertical) with gap |
| Card grids | `Stack` with wrap enabled, or `Grid` for fixed-column layouts |
| Content containers | `Frame` with constrained width (see design system) |
| Text blocks | `Text` with Framer text styles |
| Images | `Frame` with image fill or `Image` component |
| Icons | `Frame` with SVG fill or icon component |

### Key Framer features used

- **Breakpoints** — Desktop (1200px+), Tablet (810px–1199px), Mobile (0–809px)
- **Variables** — Brand colours, spacing scale, type scale, radius tokens
- **Text Styles & Colour Styles** — Linked to Variables for site-wide updates
- **Components** — Navbar, footer, CTA buttons, cards, form fields, accordions
- **CMS Collections** — Treatments, Doctors, Journal Posts, Testimonials
- **Forms** — Appointment booking form with validation
- **Page transitions** — Subtle fade or none (no elaborate page animations)
- **Scroll variants** — Reveal-on-scroll for sections (subtle, not distracting)

### What Dentiva deliberately avoids

- Custom React/TypeScript Code Components (not needed for this template)
- Third-party npm dependencies
- Elaborate scroll-jacking or parallax effects
- CSS that bypasses Framer's breakpoint system
- Hard-coded pixel values that break responsive behaviour

---

## Reusable sections

The following sections appear on multiple pages and should be built as Framer
Components so they stay in sync:

| Component | Used on |
|-----------|---------|
| Navbar (with mobile menu) | Every page |
| Footer (5-column) | Every page |
| Appointment CTA banner | Home, Treatments, About, Journal |
| Treatment card | Treatments index, Home (featured), Treatment Detail (related) |
| Doctor card | Doctors index, Home (featured) |
| Testimonial card | Home, Treatment Detail, About |
| Journal card | Journal index, Home (latest) |
| Accordion (FAQ) | Home, Treatment Detail, Pricing |
| Contact form | Contact, Treatment Detail (sidebar) |
| Section wrapper | Every section (consistent max-width and padding) |

---

## Optional premium extensions

These are documented as optional upsells or future additions. They are not
part of the core template but are designed so they can be added without
restructuring the site.

| Extension | Effort | Value |
|-----------|--------|-------|
| Online booking integration (Calendly / NexHealth embed) | Low | High — replaces the static form with live scheduling |
| Multi-location switcher | Medium | Medium — useful for group practices |
| Treatment cost calculator | Medium | Medium — interactive pricing tool |
| Virtual consultation request flow | Low | Medium — adds a second conversion path |
| Patient portal link | Low | Low — link to external portal |
| Language switcher (EN / AR / FR) | High | Medium — for international clinics |
| Dark mode | High | Low — not a priority for this audience |
| Blog with filters and search | Medium | Medium — enhances the Journal section |

---

## Project status checklist

### Phase 1 — Planning ✅ *(current)*

- [x] Project brief
- [x] Site copy (all pages)
- [x] Design system
- [x] Page architecture
- [x] QA checklist
- [ ] Competitor review (3–5 dental clinic sites)

### Phase 2 — Framer build

- [ ] Variables created (colours, spacing, typography)
- [ ] Text Styles and Colour Styles linked to Variables
- [ ] Shared components built (navbar, footer, cards, CTA, form fields)
- [ ] CMS collections configured with sample data
- [ ] Home page assembled
- [ ] Inner pages assembled
- [ ] Forms configured with validation
- [ ] SEO and Open Graph set on every page
- [ ] Responsive review (desktop, tablet, mobile)

### Phase 3 — QA and publishing

- [ ] QA checklist completed
- [ ] Content reviewed by a dental professional
- [ ] Accessibility audit (colour contrast, keyboard, screen reader)
- [ ] Performance audit (Lighthouse ≥ 90)
- [ ] Marketplace preview images created (2400×1600, 800×600)
- [ ] `framer.json` manifest completed
- [ ] Template description written for Marketplace listing
- [ ] Remix test (import into fresh Framer project, customise, publish)
- [ ] Final review and submission
