# Project Report
## Departmental Website Redesign — Department of Computer Engineering, Ahmadu Bello University

---

## 1. Project Overview

This report documents the design and development of a redesigned official
website for the Department of Computer Engineering, Faculty of Engineering,
Ahmadu Bello University (ABU), Zaria. The site was built as a static,
multi-page HTML5/CSS3 website comprising eight core pages: Home, About the
Department, Academic Programs, Staff Directory, Student Directory, News &
Events, Admissions, and Contact Us.

The brief required a professional, responsive, standards-compliant site
suitable for representing an academic department to prospective students,
current students, staff, and the public.

## 2. Technology Stack

| Layer | Technology | Notes |
|---|---|---|
| Structure | HTML5 | Semantic tags (`header`, `nav`, `main`, `article`, `section`, `footer`) throughout |
| Styling | CSS3 (Flexbox + Grid) | Single shared stylesheet, no framework dependency |
| Interactivity | CSS-only (`:hover`, `:focus`, checkbox-hack nav) | No JavaScript used anywhere on the site |
| Forms | Native HTML `<form>` via Formspree | Standards-compliant POST submission, no custom backend |
| Maps | Embedded Google Maps iframe | No API key or JS SDK required |
| Hosting (recommended) | GitHub Pages | Free static hosting, HTTPS by default |

No content management system, build tooling, or JavaScript framework was
used. Every page is a plain, hand-authored `.html` file linked to one
shared `assets/css/style.css`.

## 3. Site Architecture

```
/
├── index.html          Home
├── about.html           About the Department
├── programs.html        Academic Programs
├── staff.html           Staff Directory
├── students.html        Student Directory
├── news.html             News & Events
├── admissions.html      Admissions
├── contact.html          Contact Us
└── assets/
    ├── css/style.css     Shared stylesheet
    └── images/            Logo, photos (to be supplied)
```

Every page shares an identical header (top contact bar, logo/brand, primary
navigation) and footer (department summary, quick links, contact details,
copyright), ensuring consistent navigation and branding across the site.
The active page is marked in the nav via `aria-current="page"` for both
visual and assistive-technology clarity.

## 4. Design Rationale

The visual identity uses a navy-and-gold palette, evoking a traditional
academic institution while remaining modern and legible. Navy
(`#0d1b3e`) anchors the header, footer, and hero sections; gold
(`#d4a017`) is reserved for calls-to-action, active nav states, and
accents, keeping it meaningful rather than decorative. Body content sits
on a light neutral background (`#f5f7fb`) for readability and contrast.

Layout follows a mobile-first responsive approach: card grids
(`grid-2` / `grid-3` / `grid-4`) collapse to fewer columns as viewport
width narrows, and the primary navigation collapses into a CSS-only
"hamburger" menu (via the checkbox-hack pattern) below 960px — achieving
mobile interactivity without any JavaScript.

Each page follows a consistent content pattern — a hero banner
introducing the page's purpose, followed by card-based or tabular content
sections, and closing with a call-to-action where relevant (e.g., linking
Programs → Admissions, About → Programs).

## 5. Content Status: Verified vs. Placeholder

Where possible, content was cross-checked against the department's real,
publicly available website (`engineering.abu.edu.ng`) rather than
invented outright. The table below summarizes what is verified and what
still requires input from the department before the site can go live.

| Content Area | Status |
|---|---|
| University founding year (1962), Faculty origins (1955) | Verified against official history |
| Department's stated objectives | Verified — sourced from Article 4 of the University's Laws |
| Current academic staff names and ranks (HOD, Professors, Lecturers) | Verified against the department's staff listing |
| UTME subject requirements and admission aggregate formula | Verified against ABU's published admissions criteria |
| Postgraduate program names (PGD, M.Sc., PhD) | Corrected to match real offerings (no M.Eng. exists) |
| Department X/Twitter handle (@CompEngABU) | Verified |
| Staff emails, phone numbers, office locations | **Placeholder** — not publicly listed |
| Specific laboratory/facility names | **Placeholder** — real page content not accessible during research |
| CESA student executive names, class rep contacts | **Placeholder** — requires input from current student leadership |
| News items and event dates | **Placeholder/illustrative** — needs live department input |
| Department direct phone number | **Placeholder** |

## 6. Accessibility & Standards Compliance

- Semantic HTML5 landmarks throughout, aiding screen-reader navigation.
- All images require `alt` text (marked in templates; final text depends on real images supplied).
- Form fields use associated `<label>` elements, not placeholder-only inputs.
- Tables use `<caption>`, `<thead>`, and scoped `<th>` headers for correct data-table semantics; visually-hidden captions (`.sr-only`) are provided for tables where a visible caption wasn't desired.
- Focus states are visible on all interactive elements (`:focus-visible` styling), supporting keyboard-only navigation.
- Colour contrast between text and backgrounds meets WCAG AA thresholds for body text.

## 7. Known Limitations

- The contact form depends on a third-party service (Formspree); the
  placeholder form ID must be replaced with the department's real
  endpoint before submissions will work.
- The embedded Google Map uses a general ABU Zaria query rather than a
  precise pinned department location, since exact building coordinates
  weren't available.
- Some department subpages (laboratories, lecture halls) exist on the
  live official site but returned no retrievable content during
  research — likely due to dynamic rendering — so facility descriptions
  remain general rather than specific.

## 8. Deployment Recommendation

The site is fully static and requires no server-side runtime or
database, making **GitHub Pages** the most appropriate low-cost
deployment option: free hosting, automatic HTTPS, and redeploys
automatically on every push to the repository. The recommended
structure places all files at the repository root (or under a
`/docs` folder) with GitHub Pages configured to serve from that
branch/folder. A custom domain can be attached later via a `CNAME`
file if the department wants a branded URL instead of the default
`github.io` subdomain.

## 9. Next Steps Before Going Live

1. Supply real staff photos, emails, and phone numbers.
2. Confirm exact laboratory/facility names and descriptions with the department.
3. Obtain current CESA executive and class representative details.
4. Replace the Formspree placeholder ID with a live form endpoint.
5. Confirm current admission cut-off marks and key dates for the active academic session, since these change yearly.
6. Add the department's official logo image in place of the placeholder brand mark.
