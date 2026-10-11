# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A static one-page website for the Czech punk band MOPED 56, plus a print-oriented
promo sheet for event organizers. No build step, no npm, no dev server, no tests.
Edit the HTML/CSS and reload the file in a browser.

Site content and `docs/` are in Czech; code comments are in English.

## Files

- `index.html` + `style.css` — the whole website (single page, sections `#kapela`,
  `#diskografie`, `#poradatele`, `#booking`)
- `promo.html` — source of the A4 promo sheet, self-contained `<style>` with
  `@page { size: A4 }` and `.page { page-break-after: always }`
- `Moped56-promo.pdf` — rendered output of `promo.html`, linked from the site
- `assets/cover.jpg` — album cover (square, currently 520×520)
- `docs/` — Czech notes: content editing, PDF regeneration, publishing, visual style

## Regenerating the promo PDF

After any change to `promo.html`:

```bash
cd ~/dev/moped56
"/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --headless --disable-gpu --no-pdf-header-footer --virtual-time-budget=8000 \
  --print-to-pdf="$PWD/Moped56-promo.pdf" "file://$PWD/promo.html"
```

Chrome works identically (different binary path). `--virtual-time-budget=8000`
exists so the Oswald web font loads; without it the PDF sets in a system font.

Verify the result is exactly 2 pages:

```bash
pdfinfo Moped56-promo.pdf | grep Pages
```

More than 2 means something overflowed page 1. Shorten the text — do not shrink
the type; page 1 is deliberately full down to the contact footer.

## Content duplication

Lineup, technical specs and discography exist in **both** `index.html` and
`promo.html`. Changing one requires checking the other and regenerating the PDF.

## Design constraints

Colors live as CSS variables at the top of `style.css` (`--ink`, `--paper`,
`--red`, …) — change them there, not inline. Headings use Oswald from Google
Fonts; body text is a system sans stack. The aesthetic is poster-like: no
gradients, no shadows, no rounded corners.

**Diacritics trap:** multi-line all-caps headings with carons need
`line-height` of at least 1.22. Lower values make the caron of `Ě` on the second
line collide with the first line (the album title read as `AŤ SE, DĚJE` at 0.98,
and the artifact was still visible at 1.16). Always look at the rendered result,
not just the code. See `docs/design.md`.

The first `<li>` of `.records` is styled red automatically as the newest record,
so new albums go at the top of the list.

## Publishing

GitHub Pages, branch `main`, folder **`/ (root)`** — not `/docs`, which holds
documentation rather than the site. Live at https://moped56.cz (`CNAME` file,
HTTPS enforced); every push to `main` deploys. `robots.txt` and `sitemap.xml`
sit in the root — bump `<lastmod>` on bigger content changes. See
`docs/publikace.md`.
