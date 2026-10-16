# Project overview

CodeWithUs is a collaborative website project for an online coding bootcamp. Its central message is **“Learn to code. Change your career.”** The site introduces the learning experience, explains the course options, and guides visitors toward a conversation or application.

The bootcamp and its outcomes are the assignment's business concept. This repository implements the website presentation; it does not provide live classes, manage students, or process applications.

## Audience

- Career-changers, particularly people aged 25–40 who want to move into tech.
- University graduates without a computer science background.
- Self-taught learners who want structure and accountability.
- Beginners seeking guidance from a mentor rather than video-only learning.

## Bootcamp concept

The proposed learning experience combines live coding classes, one-to-one mentorship, six portfolio projects, and career preparation. The course page presents a 12-week full-time path and a 24-week part-time path.

Four tracks describe the learning journey:

1. **Frontend Foundations:** HTML, CSS, Flexbox, responsive design, and accessibility.
2. **JavaScript Essentials:** language fundamentals, the DOM, APIs, and asynchronous code.
3. **Full-Stack Project:** a deployed application using a server and database.
4. **Career Launch:** portfolio and CV reviews, interview practice, and hiring preparation.

These subjects describe the bootcamp curriculum. The website itself uses HTML and CSS only.

## Pages and visitor journey

| Page | Purpose | Implementation status |
| --- | --- | --- |
| Home | Introduce the promise, benefits, testimonial, and next step | Main content sections implemented |
| Courses | Explain tracks, learning steps, and study schedules | Content implemented; shared header pending |
| Contact | Let visitors explore their questions and learn about the team | Content implemented; form delivery disabled |
| Sign up | Collect an application and explain the next steps | Scaffold only |

The planned main journey is **Home → Courses → Contact → Sign up → Home**. The first three CTA transitions exist. The Sign up page does not yet complete the loop. The shared footer links to every page.

## Design direction

The Studio Grid identity uses a restrained palette and flat, readable sections. “Studio Grid” is the visual identity's name; CSS Grid is not used for layouts.

| Role | Color |
| --- | --- |
| Header, hero, footer, primary text | Dark `#1F2937` |
| Buttons and section accents | Blue `#3882F6` |
| Testimonial/about backgrounds and borders | Light gray `#E5E7EB` |
| Main backgrounds and inverse text | Off-white `#F9FAF8` |

Roboto is the sole typeface. The shared scale uses 4, 8, 16, 24, 32, 48, and 96px spacing, an 1100px maximum container, and 8px component corners. Layouts use Flexbox, with smaller headings and stacked content on mobile. Gradients, glass effects, neon effects, and decorative blobs are outside the design rules.

## Collaboration and ownership

| Contributor | Landing-page responsibility | Sub-page |
| --- | --- | --- |
| Tony | Header, navigation, and hero | Sign up |
| Lefa | Information section | Courses |
| Karim | Quote, CTA, and footer | Contact |

Tony owns the shared navigation and Karim owns the shared footer. Coordinate changes with the owner and copy approved shared markup rather than creating different versions on each page. Work takes place on feature branches, followed by a pull request and teammate review before merging into `main`.

## Project boundaries

This repository contains static pages and assets. It has no JavaScript runtime, backend, database, payment processing, account system, or application-delivery service. Contact details, the graduate story, and cohort deadline are supplied or mock project content, not verified operational information.

Before submission, finish the application page, complete the shared header and mobile menu, check responsive layouts and links, and complete the assignment's team and AI-use requirements. The [architecture document](architecture.md) explains the current implementation and its known limitations.

[Back to README](../README.md)
