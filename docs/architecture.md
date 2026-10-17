# Architecture

CodeWithUs is a static, multi-page website. A browser loads each HTML document directly, applies its CSS, and fetches local images plus external font/icon assets. There is no application router, templating engine, build pipeline, backend, or database.

## Repository structure

```text
code-with-us/
├── README.md                    # Setup and documentation entry point
├── AGENTS.md                    # Assignment and collaboration rules
├── CONTRIBUTING.md              # Currently an empty placeholder
├── docs/
│   ├── overview.md              # Product concept and project scope
│   └── architecture.md          # Implementation and maintenance guide
└── public/                     # Static site root
    ├── index.html
    ├── courses.html
    ├── contact.html
    ├── signup.html
    ├── css/
    │   ├── main.css
    │   ├── theme.css
    │   ├── layout.css
    │   ├── components.css
    │   ├── quote-cta-footer.css
    │   └── contact.css
    └── img/                    # Logo, hero variants, and benefit-card photos
```

Serve or publish `public/` as the site root. For example, `/courses.html` maps directly to `public/courses.html`. Links and image paths are relative, so the directory structure must stay intact.

The [GitHub Pages workflow](../.github/workflows/deploy-pages.yml) uploads `public/` directly and deploys it on pushes to `main`, with no build step. It can also be run manually from the Actions tab on `main`; runs from other branches are skipped. Before its first deployment, set **Settings → Pages → Build and deployment → Source** to **GitHub Actions** in the repository. Merge the workflow into `main` to enable automatic deployment. Deployments use the `github-pages` environment and the built-in `GITHUB_TOKEN`; no custom secret is required.

## Stylesheet responsibilities and loading order

Every page links to `css/main.css`. That file imports the shared styles in this order:

```text
main.css
  → theme.css
  → layout.css
  → components.css
  → base typography, responsive image defaults, and link defaults
```

| File | Responsibility |
| --- | --- |
| [theme.css](../public/css/theme.css) | Google Fonts import; palette, spacing, typography, radius, and transition variables |
| [layout.css](../public/css/layout.css) | Reset, `.container`, `.section`, `.page-hero`, and Flexbox `.row` / `.row-center` helpers |
| [components.css](../public/css/components.css) | Shared buttons, header/navigation, hero, information cards, quote, CTA, footer, forms, FAQs, and course-page components |
| [main.css](../public/css/main.css) | Shared entry point and base element styles |
| [quote-cta-footer.css](../public/css/quote-cta-footer.css) | Testimonial italic font, quote alignment, CTA sizing, footer wrapping/focus, and section adjustments |
| [contact.css](../public/css/contact.css) | Contact columns, detail rows, form sizing, about strip, and mobile adjustments |

All pages link to `quote-cta-footer.css` after `main.css`. Contact additionally loads `contact.css` after those files. Each page also links to Font Awesome from cdnjs for icons. Later rules can override earlier rules according to selector specificity, so preserve the load order.

Use the existing custom properties and classes before adding CSS. Keep additions specific to the section or page and load them in a separate stylesheet when needed. The assignment's original single-file example is implemented here as these modular stylesheets; the actual entry point is `main.css`, not `style.css`.

## Page composition and shared markup

Each document uses semantic page regions: a site header, a `main` element containing content sections, and a site footer. Individual content groups use articles, a blockquote, an address, or a form where appropriate.

There are no reusable HTML includes. Shared markup is copied into pages manually:

- The footer is present on all four pages with the same navigation and social links.
- Home and Contact contain Tony's header markup. Courses and Sign up still contain header placeholders.
- Buttons reuse `.btn` and `.btn-outline`; CTA boxes reuse `.cta-box` and `.cta-text`.
- Contact uses the shared `.form-card` and `.form-group` classes, with page-specific additions.

To update a shared component, coordinate with its owner, update the approved version, and copy it into each page that uses it. Check the pages together to prevent their markup or behavior from drifting.

## Responsive layout and assets

Flexbox handles the main layouts. `.container` limits content to 1100px with 24px horizontal padding. `.section` provides 96px vertical padding on desktop and 48px through the existing tablet/mobile rules. Component-specific rules may adjust this further.

Mobile rules use `max-width: 767px`; tablet rules use `min-width: 768px` and `max-width: 1199px`. Base styles cover larger screens. The brief calls for a burger menu at 768px and below, but the current shared navigation rules switch below 768px and the required checkbox markup is still absent.

Contact wraps its introduction and form into a single column when their Flexbox bases no longer fit. Form fields stack on mobile. The homepage hero uses `srcset` with 704px and 1408px images; global image styles apply `max-width: 100%` and automatic height. Benefit-card photos use fixed display heights with `object-fit: cover`.

Google Fonts provides Roboto, including a separate light italic face for the quote. Font Awesome supplies the social and contact icons. These external assets need network access; local content remains available if the services cannot load, but fonts or icons may differ or be missing.

## Forms and data

The Contact form contains name, email, subject, and message fields. Labels are associated using `for` and `id`. Required fields, email input type, and maximum lengths use native browser validation without JavaScript.

The form has no delivery endpoint. Its send button is disabled and the page identifies it as a demo. Nothing is intentionally submitted, stored, or emailed by this implementation. The email uses the reserved `.example` domain, the phone is mock data, and social links lead to platform homepages.

Sign up currently has no application form. Connecting either page to a service would require a separate decision about delivery, validation, and handling of personal data.

## Current limitations

These are existing implementation gaps, not features completed by the documentation:

- Sign up contains a hero and footer but lacks its application form, next-step content, and FAQ.
- Courses and Sign up lack the shared header. Home and Contact use extensionless `contact` and `courses` header links, which do not resolve with a basic static server.
- Burger styles exist, but header markup lacks the checkbox and label that open the menu. Mobile rules currently hide its navigation without an opener.
- The homepage hero has shown horizontal overflow at mobile/tablet widths and needs further responsive work.
- The homepage hero's “Sign Up” button has no navigation target. The later homepage CTA links to Courses.
- Contact sending is disabled. Testimonials, contact information, cohort copy, and social destinations are demo content.
- There is no automated test runner configured. The Pages workflow deploys static assets without running tests. `CONTRIBUTING.md` is currently empty; use `AGENTS.md` for the existing project rules.

## Validation when changing the site

Preview all four pages from the static root and check 375px, 768px, and 1200px or wider. Check horizontal overflow, section alignment, images, keyboard focus, labels, required fields, internal links, shared footer consistency, and the mobile menu. Treat the gaps above as remaining work rather than evidence that those checks already pass.

Use `git diff --check` before committing, and inspect changes for accidental JavaScript, CSS Grid, or changes to another contributor's component. No package installation or build command is required.

[Project overview](overview.md) · [Back to README](../README.md)
