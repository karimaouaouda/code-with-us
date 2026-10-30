
## Stage 5 — article→figure/figcaption conversion (Tony, Oct 2026)
- Examiner rule: articles only for *unrelated* standalone text; landing cards are related in-flow content.
- Mapping decided: image cards (index) → `figure`/`figcaption` (img + captioned h3+p); text-only cards (courses, contact) → `section` (thematic block with heading — no caption abuse on bare text).
- Learned: `figcaption` is for labeling self-contained media; misusing it on plain text both reads wrong and offers no semantics gain. `section` conveys "thematically related part of this page," which is exactly what a text card is.
- One CSS selector updated (contact.css `.contact-about-columns article` → `section`); all other card styling is class-based.
