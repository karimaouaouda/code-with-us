
## Stage 5 — article→figure/figcaption conversion (Tony, Oct 2026)
- Examiner rule: articles only for *unrelated* standalone text; landing cards are related in-flow content.
- Mapping decided: image cards (index) → `figure`/`figcaption` (img + captioned h3+p); text-only cards (courses, contact) → `section` (thematic block with heading — no caption abuse on bare text).
- Learned: `figcaption` is for labeling self-contained media; misusing it on plain text both reads wrong and offers no semantics gain. `section` conveys "thematically related part of this page," which is exactly what a text card is.
- One CSS selector updated (contact.css `.contact-about-columns article` → `section`); all other card styling is class-based.

## Stage 6 — comment restore (Tony, Oct 31 2026)
- Stripped all comments in 89609a5, then restored them on `dev` (branch of fix/article-header-formatting) via checkout of 0fe5767's public/ tree.
- Learned: pure-deletion commits (0 insertions) revert cleanly and provably — the numstat check (insertions only) is the proof no code changed.
- Decision: keep comments in production code for team readability; spec Part 7's numbered section banners stay.
