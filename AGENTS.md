PART 1 — PROJECT DESCRIPTION
Project Name
CodeWithUs — an online coding bootcamp.

What the Company Does
CodeWithUs is a 12-week online bootcamp that takes complete beginners and turns them into job-ready web developers. It offers live classes, 1-on-1 mentorship, real portfolio projects, and career support until graduates sign their first developer role.

Target Audience
Career-changers (25–40) who want to move into tech

University graduates who didn't study computer science

Self-taught learners who need structure and accountability

People who want a mentor, not just video tutorials

Why This Concept
The four required landing page sections map naturally to a bootcamp:

Hero → the promise ("Learn to code. Change your career.")

Random Information → four reasons the bootcamp works

Quote → a graduate's testimonial

Call to Action → apply now / next cohort deadline

This means no section feels forced or padded.

Pages (4 total)
Page	File	Purpose
Home / Landing	index.html	Follows the client's rough design exactly
Courses	courses.html	Course tracks, how it works, pricing
Sign up	signup.html	Application form, what happens next, FAQ
Contact	contact.html	Contact form, details, about strip
All pages share the same nav and footer, and follow the same visual identity.

PART 2 — TEAM & OWNERSHIP
Member	Landing Page Blocks	Sub-Page
Tony	Header + Nav · Hero	signup.html
You	Random Information	courses.html
Karim	Quote · Call to Action · Footer	contact.html
Shared Component Owners
Component	Owner	Rule
Nav	Tony	Tony writes it. Others copy it unchanged.
Footer	Karim	Karim writes it. Others copy it unchanged.
Never edit someone else's shared component. Ask the owner if you need a change.

PART 3 — LOGO
Property	Value
Format	Text + CSS pseudo-element, or AI-generated JPG
Text	CodeWithUs
Font	Roboto 900, 24px
Color	#F9FAF8 (text), #3882F6 (mark)
Mark	{ } in #3882F6, 12px gap before text
Background	Transparent (sits on #1F2937 header)
Mobile	Same logo, 20px
HTML:

html
<a href="index.html" class="logo">Code<span class="logo-accent">With</span>Us</a>
CSS:

css
.logo {
  display: flex;
  align-items: center;
  gap: 12px;
  font: 900 24px 'Roboto', sans-serif;
  color: var(--white);
  text-decoration: none;
}
.logo::before {
  content: "{ }";
  color: var(--blue);
  font-weight: 700;
}
.logo-accent {
  color: var(--blue);
}
If using an AI-generated JPG, save it as img/logo.jpg and use:

html
<a href="index.html" class="logo">
  <img src="img/logo.jpg" alt="CodeWithUs logo" class="logo-img">
</a>
css
.logo-img { height: 40px; width: auto; display: block; }
PART 4 — VISUAL IDENTITY (Studio Grid)
Colors (Client-mandated)
css
:root {
  --dark: #1F2937;
  --blue: #3882F6;
  --light: #E5E7EB;
  --white: #F9FAF8;
  --blue-hover: #2f6fd6;
  --text-muted: #6B7280;
  --shadow: 0 4px 12px rgba(31, 41, 55, 0.08);
}
Typography — Roboto only
Element	Size	Weight	Color
Hero headline	48px	900	--white
Hero subtext	18px	400	--light
Section heading	36px	700	--dark
Card title	20px	700	--dark
Card caption	16px	400	--text-muted
Body text	18px	400	--dark
Quote	36px	300 italic	--dark
Quote attribution	16px	700	--dark
Nav link	18px	400	--light
Logo	24px	900	--white
Button	16px	700	--white
Spacing Scale
text
4 / 8 / 16 / 24 / 32 / 48 / 96px
Section padding: 96px desktop, 48px mobile
Container: max 1100px, centered
Section Background Rhythm
text
Header + Nav     → --dark
Hero             → --dark
Random Info      → --white
Quote            → --light
Call to Action   → --white (blue box inside)
Footer           → --dark
Visual Rules
8px radius on cards and buttons

Hover-only shadows (flat by default)

Blue used only for buttons + one accent line per section

No gradients

No glassmorphism

No floating blurry cards

No glowing blobs

No neon effects

No decorative icons — icons only when they improve usability

Transitions: 0.2s ease only

PART 5 — TECHNICAL RULES
Required by the assignment
Rule	Status
Semantic HTML	<header>, <nav>, <main>, <section>, <article>, <footer>
Vanilla CSS	No frameworks
At least one external stylesheet	css/style.css
Flexbox for main layouts	Required everywhere
Media queries	Required
Responsive images	<picture> / srcset / CSS media queries
Roboto font imported	Google Fonts
Shared nav + footer	Same on all pages
CSS-only burger menu	Checkbox hack, no JS
Collaborative GitHub repo	All 3 commit
Strictly forbidden
Forbidden	Notes
CSS Grid	Not allowed anywhere
JavaScript	Not allowed, including the burger menu
CSS libraries	Only Font Awesome, and only for icons
Frameworks	No Bootstrap, no Tailwind, nothing
Allowed
Google Fonts (Roboto)

Font Awesome (icons only)

Pure HTML + CSS

PART 6 — RESPONSIVE RULES
Test at these widths:

Device	Width
Mobile	375px
Tablet	768px
Desktop	1200px+
At every width
No horizontal scrolling

Text readable

Images fit inside containers, not stretched

Flexbox layouts reorganize when needed

Nav becomes a burger menu at ≤768px

All pages usable

No overlapping sections

No disappearing content

Breakpoints
css
@media (max-width: 767px) { ... }                              /* Mobile */
@media (min-width: 768px) and (max-width: 1199px) { ... }      /* Tablet */
@media (min-width: 1200px) { ... }                             /* Desktop */
Mobile adaptations
Nav → burger menu

Hero → stacked column (text top, image bottom)

Info cards → 1 per row

Headings shrink: hero 32px, section 28px, quote 24px

Section padding: 48px

PART 7 — FILE STRUCTURE
text
codewithus/
├── index.html
├── courses.html
├── signup.html
├── contact.html
├── css/
│   └── style.css
├── img/
│   ├── logo.jpg
│   ├── hero.jpg
│   ├── card-1.jpg ... card-4.jpg
│   └── ...
├── AI-LOG.md
└── README.md
CSS file order (strict)
css
/* 1. Font import + reset */
/* 2. Variables */
/* 3. Base typography */
/* 4. Layout helpers */
/* 5. Shared: header, nav, burger */
/* 6. Hero */
/* 7. Random information */
/* 8. Quote */
/* 9. Call to action */
/* 10. Footer */
/* 11. Sub-pages */
/* 12. Media queries */
PART 8 — CLASS NAME CONTRACT
Use these exact names. No variations.

css
/* Layout */
.container, .section

/* Header + Nav (Tony) */
.site-header, .main-nav, .nav-list, .nav-link,
.nav-link--active, .burger, .burger-icon, .nav-toggle,
.logo, .logo-accent, .logo-img

/* Hero (Tony) */
.hero, .hero-text, .hero-image

/* Random Information (You) */
.info-section, .info-heading, .info-cards,
.info-card, .info-card img, .info-card p

/* Quote (Karim) */
.quote-section, .quote-text, .quote-author

/* CTA (Karim) */
.cta-section, .cta-box, .cta-text, .cta-btn

/* Footer (Karim) */
.site-footer, .footer-inner, .footer-links, .footer-socials

/* Sub-pages */
.page-hero, .page-hero h1, .page-hero p
PART 9 — BUILD ORDER
Nav and footer block everyone, so build them first.

Tony builds nav + hero → PR → review → merge to main

Karim builds footer → PR → review → merge to main

Everyone pulls main to get the latest nav + footer

Then build in parallel:

You → Random Information + courses.html

Tony → finish hero + signup.html

Karim → Quote + CTA + contact.html

PART 10 — GIT WORKFLOW
main = stable, always working

Branches:

feature/header-nav-hero (Tony)

feature/random-info (You)

feature/quote-cta-footer (Karim)

feature/courses-page (You)

feature/signup-page (Tony)

feature/contact-page (Karim)

Rules
Pull main daily

Commit small and often

Never push directly to main

Every branch → PR → one teammate reviews → merge

If you need a change in someone else's component, message them — don't edit it

PART 11 — PAGE LOOP (CTA LINKS)
Each page's CTA links to the next, so the site feels connected:

text
index.html → courses.html → contact.html → signup.html → index.html
PART 12 — TEST CHECKLIST (EVERY PAGE)
□ No horizontal scrolling at 375px
□ No horizontal scrolling at 768px
□ No horizontal scrolling at 1200px+
□ Text readable at all sizes
□ Images fit containers, not stretched
□ Nav becomes burger at ≤768px
□ Burger opens/closes (CSS only)
□ No overlapping sections
□ No disappearing content
□ All 4 pages link correctly
□ Roboto everywhere
□ Palette matches
□ No CSS Grid anywhere
□ No JavaScript anywhere
PART 13 — AI USAGE RULES
The assignment requires AI to be used in at least 4 different stages.

Process
Think → Try → Ask AI → Understand → Test → Accept / Modify / Reject

Rules
Ask AI to explain concepts, not just to write code

Don't ask AI to fix a problem before your team has attempted it

Near the end, ask AI to review part of your work

Decide as a team which suggestions to keep

Log every AI use in AI-LOG.md
Stage	Who	Asked	Outcome
1	Tony	Burger menu explanation	...
2	You	Responsive image technique	...
3	Karim	Semantic HTML review	...
4	All	Final review	...
Log what you learned, not just what AI gave you.

PART 14 — CONTENT (Landing Page)
Header + Nav (Tony)
Logo: { } CodeWithUs

Links: Home · Courses · Sign up · Contact

Hero (Tony)
Headline: Learn to code. Change your career.

Subtext: CodeWithUs is a 12-week online bootcamp that takes you from zero to job-ready web developer — with live mentors, real projects, and a portfolio that gets you hired.

Button: Apply now

Image: student coding at a laptop

Random Information (You)
Heading: Why CodeWithUs works

Card 1: Live coding classes — Learn from working developers in daily live sessions — not pre-recorded videos.

Card 2: 1-on-1 mentorship — Get paired with a mentor who reviews your code and guides your career.

Card 3: Real projects — Build 6 portfolio projects, including a full-stack app deployed live.

Card 4: Career support — CV reviews, mock interviews, and introductions to hiring partners.

Quote (Karim)
"I was a marketing manager with zero coding experience. Twelve weeks later I deployed my first full-stack app — and three weeks after graduating, I signed my first developer contract. CodeWithUs didn't just teach me to code. It changed what I thought was possible."
— Aisha, 2024 graduate (now Junior Developer)

Call to Action (Karim)
Heading: Ready to start? It's time!

Subtext: Applications for the next cohort close on Friday. Reserve your spot now.

Button: Apply now (white outline)

Footer (Karim)
© 2025 CodeWithUs. All rights reserved.

Small links: Home · Courses · Sign up · Contact

Font Awesome icons: GitHub, LinkedIn, Twitter

PART 15 — SUB-PAGE CONTENT
courses.html (You)
Short dark page-hero: "Our Courses"

4 course tracks: Frontend Foundations · JavaScript Essentials · Full-Stack Project · Career Launch

How it works: Apply → Learn → Get hired

Pricing: Full-time (12 weeks) · Part-time (24 weeks)

CTA: "Not sure which track? Talk to us." → contact.html

signup.html (Tony)
Short dark page-hero: "Apply to CodeWithUs"

Application form: Full name · Email · Track dropdown · Start date · Message · Submit

What happens next: 1. We review → 2. Interview → 3. Offer

FAQ: 4 questions

CTA: "Questions first?" → contact.html

contact.html (Karim)
Short dark page-hero: "Get in touch"

Contact form: Name · Email · Subject · Message · Send

Contact details: Email · Phone · Office (Font Awesome icons)

About strip: Who we are · What we believe

CTA: "Ready to apply?" → signup.html

PART 16 — SANITY CHECK
Before submission, confirm:

□ 4 pages built
□ Every landing block owned and completed
□ Nav owned by Tony, footer owned by Karim
□ No CSS Grid used anywhere
□ No JavaScript used anywhere
□ Roboto imported and used everywhere
□ Flexbox used for all main layouts
□ Media queries at 767 / 1199 / 1200
□ CSS-only burger menu works
□ All pages test clean at 375 / 768 / 1200
□ All CTA links point to the right next page
□ AI-LOG.md complete with at least 4 entries
□ All 3 members have commits on the repo
□ README.md explains the project
