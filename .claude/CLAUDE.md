# Editing guide for this repository

This repository IS the live website thesalsal.org. Every push to `main` publishes within about a minute, so check your change before you commit.

## Scope
- In scope: text, links, images, PDFs, news items, webinar details, board bios.
- Out of scope without the site owner's approval: navigation structure, page layout, the CSS system, new sections, deleting pages.

## How the site is built
- One folder per page (`about/index.html` style). URLs are clean: never link to a `.html` file.
- The navigation and footer live in ONE place: `partials/nav.html` and `partials/footer.html`. Never edit the HTML between `<!-- NAV:START -->`/`<!-- NAV:END -->` or `<!-- FOOTER:START -->`/`<!-- FOOTER:END -->` inside a page; it is overwritten.
- After changing a partial or adding a page, run `python3 build.py` and commit everything it changed. It stamps the nav and footer into every page and regenerates canonical URLs, `sitemap.xml` and `robots.txt`.
- The homepage (`index.html`) is self-contained: its CSS is inline in its own `<style>` and it does not load `assets/site.css`. Interior pages do load `assets/site.css`.
- News: edit `assets/news-data.js` only. The homepage and the News page both render from it.
- Board bios: edit `assets/board-bios.js` (keys match the board photo filename).

## House rules
- Never crop faces: portraits use `object-fit: cover` with `object-position: center top`.
- No em dashes or double hyphens in any copy.
- The public Sponsorship page shows no prices.
- Never link a raw Jotform URL; forms are embedded inside a page on this site.
- Keep commits small, one change each, with a plain message saying what changed and on which page.
