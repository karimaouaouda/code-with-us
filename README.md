# CodeWithUs

A four-page website for an online coding bootcamp, built collaboratively with semantic HTML and vanilla CSS. The bootcamp concept focuses on live classes, mentorship, portfolio projects, and career support for beginners moving into web development.

This is a front-end assignment and demo. Contact details are mock data, and forms are not connected to a service.

## Run locally

There are no packages to install or assets to build. From the repository root, use Python 3 to serve the site:

```sh
python -m http.server 8000 --directory public
```

Open [http://localhost:8000](http://localhost:8000). Stop the server with `Ctrl+C`. If Python is unavailable, open `public/index.html` directly in a browser or use an editor's static preview server.

Internet access is needed for Google Fonts and Font Awesome. The HTML, local CSS, and project images are served from `public/`.

## Pages

| Page | File | Current content |
| --- | --- | --- |
| Home | [index.html](public/index.html) | Hero, four bootcamp benefits, graduate testimonial, CTA, and footer |
| Courses | [courses.html](public/courses.html) | Course tracks, learning steps, full-time/part-time options, contact CTA, and footer |
| Contact | [contact.html](public/contact.html) | Contact form, mock contact details, about section, application CTA, and footer |
| Sign up | [signup.html](public/signup.html) | Page scaffold and footer; application content is pending |

## Documentation

- [Project overview](docs/overview.md): audience, goals, page journey, design direction, team ownership, and current scope.
- [Architecture](docs/architecture.md): file structure, stylesheet loading, shared components, responsive behavior, and maintenance guidance.
- [Project instructions](AGENTS.md): assignment requirements, class-name contract, component ownership, and submission checklist.

## Working on the project

Keep the implementation in HTML and CSS. Use Flexbox for layouts; JavaScript, CSS Grid, frameworks, and general-purpose CSS libraries are outside the assignment rules. Roboto and Font Awesome icons are permitted.

Reuse the existing variables, layout helpers, and components. Keep necessary page-specific additions in separate stylesheets. Coordinate shared-header changes with Tony and shared-footer changes with Karim, then copy the approved markup across pages.

Create branches from an up-to-date `main`, make focused commits, and open a pull request for a teammate to review. Do not push directly to `main`.

## Validation and remaining work

Check all pages at 375px, 768px, and 1200px or wider. Confirm readable text, fitted images, working links, visible keyboard focus, and no horizontal scrolling. Check the mobile menu and form labels as well as the desktop layout. There is no automated test runner configured.

The application page and shared navigation still need completion. The header is missing on Courses and Sign up; Home and Contact use extensionless Contact/Courses links and lack the checkbox markup needed for the mobile menu. The homepage hero also needs responsive follow-up. Footer links provide navigation to all four HTML pages.

The contact form is explicitly a demo with sending disabled. Its email and phone are examples, social links point to platform homepages, and the cohort deadline is sample copy. See the [architecture's current limitations](docs/architecture.md#current-limitations) before treating the site as ready for real applicants.
