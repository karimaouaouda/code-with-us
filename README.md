# CodeWithUs

A four-page marketing website for a fictional online coding bootcamp.

**CodeWithUs** is a 12-week online bootcamp that takes complete beginners
and turns them into job-ready web developers. The site presents the bootcamp's
courses, mentorship model, portfolio projects, and career support.

Built as a group assignment for an AI-assisted front-end development course
at Mayerfeld Consulting — four responsive pages using semantic HTML and
vanilla CSS, developed with AI as a coding assistant.

---

## Practicum Credits

| | |
|---|---|
| **Project** | AI HTML/CSS Group Assignment |
| **Institution** | Mayerfeld Consulting |
| **Course** | AI-Assisted Front-End Development |
| **Instructor** | Branko Popovic |
| **Date** | October 2026 |
| **Repository** | [github.com/karimaouaouda/code-with-us](https://github.com/karimaouaouda/code-with-us) |

---

## Team

| Name | Role | GitHub |
|---|---|---|
| **Lefa Motsoeneng** | Random Information block · Courses page | [@Lefakatleho14](https://github.com/Lefakatleho14) |
| **Tony Thuo** | Header · Nav · Hero · Sign up page | [@tonythuo](https://github.com/tonythuo) |
| **Karim Aouaouda** | Quote · CTA · Footer · Contact page | [@karimaouaouda](https://github.com/karimaouaouda) |

---

## Pages

| Page | File | What's on it |
|---|---|---|
| **Home** | [index.html](public/index.html) | Hero, four bootcamp benefits, graduate testimonial, CTA banner, footer |
| **Courses** | [courses.html](public/courses.html) | Four course tracks, how the program works, full-time/part-time pricing, CTA |
| **Sign up** | [signup.html](public/signup.html) | Application form, next steps, FAQ, CTA |
| **Contact** | [contact.html](public/contact.html) | Contact form, contact details, about strip, CTA |

All four pages share the same navigation and footer.

---

## Tech Stack

- **Semantic HTML5**
- **Vanilla CSS** — no frameworks, no CSS libraries
- **Flexbox** for all layouts (CSS Grid is not used)
- **CSS-only burger menu** for mobile — no JavaScript anywhere
- **Roboto** from Google Fonts
- **Font Awesome** for icons only

---

## Responsive Design

Tested at three widths:

| Device | Width | Key changes |
|---|---|---|
| Mobile | 375px | Nav collapses to burger, cards stack vertically |
| Tablet | 768px | Cards wrap to two columns, nav stays horizontal |
| Desktop | 1200px+ | Full layouts, cards in a row |

No horizontal scrolling at any width. Images scale inside their containers.

---

## Design System

| Role | Color | Used for |
|---|---|---|
| **Dark** | `#1F2937` | Header, hero, footer, headings on light |
| **Blue** | `#3882F6` | Buttons, accents, active nav links |
| **Light** | `#E5E7EB` | Quote section background, borders |
| **White** | `#F9FAF8` | Page background, text on dark |

Typography uses Roboto with four weights: 300 (quote), 400 (body), 700 (headings), 900 (hero + logo).

---

## Run Locally

No packages to install. No build step.

**Option 1 — Open directly**

Open `public/index.html` in a browser. That's it.

**Option 2 — Serve with Python**

From the repository root:

```sh
python -m http.server 8000 --directory public

Then open http://localhost:8000. Stop with Ctrl+C.

Option 3 — VS Code Live Server

Right-click public/index.html → Open with Live Server.

Internet access is needed for Google Fonts and Font Awesome. All other assets are local.

Project Structure
text
code-with-us/
├── public/
│   ├── index.html              Home page
│   ├── courses.html            Courses page
│   ├── signup.html             Sign up page
│   ├── contact.html            Contact page
│   ├── css/
│   │   ├── main.css            Entry point (imports the others)
│   │   ├── theme.css           Variables + Roboto import
│   │   ├── layout.css          Containers, sections, page structure
│   │   ├── components.css      Nav, buttons, cards, forms, footer
│   │   ├── quote-cta-footer.css
│   │   └── contact.css         Contact page specifics
│   └── img/                    Logo, hero image, feature card images
├── README.md
└── AGENTS.md
Notes
This is a front-end assignment. Contact details are mock data, forms are not connected to a service, and social links point to platform homepages.

Assets
Images: Unsplash and Pexels — free to use

Font: Roboto — Google Fonts

Icons: Font Awesome 6 — free tier

License
Educational project. Not intended for commercial use.

## Apply It

### Step 1 — Open the file

powershell
code README.md

## Apply It

