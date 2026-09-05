# moped56

Web kapely MOPED 56 — jedna stránka, žádný build.

- `index.html` + `style.css` — celý web
- `promo.html` — zdroj promo materiálu pro pořadatele (A4, print CSS)
- `Moped56-promo.pdf` — vyrenderovaný materiál, na který web odkazuje
- `assets/cover.jpg` — obal alba *Ať se děje co děje*

## Dokumentace

Podrobnosti jsou v [`docs/`](docs/) — úprava obsahu, generování promo PDF,
zveřejnění a vizuální styl.

## Úpravy

Otevřít `index.html` v prohlížeči, upravit, hotovo. Žádné npm, žádný dev server.

## Přegenerování promo PDF

Po úpravě `promo.html`:

```bash
"/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --headless --disable-gpu --no-pdf-header-footer --virtual-time-budget=8000 \
  --print-to-pdf="$PWD/Moped56-promo.pdf" "file://$PWD/promo.html"
```

Funguje stejně s Chrome. Výstup musí mít 2 strany — když jich je víc, něco na
první stránce přeteklo.

## Publikace

GitHub Pages, větev `main`, kořen repozitáře. Repozitář je zatím privátní;
web se objeví až po přepnutí na public.

## Co ještě chybí

Reference z let 2024–2025, monitorové mixy, odkaz na živé video, logo ve
vektoru, odkazy na streaming a obal alba ve větším rozlišení než 520×520.
Podrobně v [docs/promo-pdf.md](docs/promo-pdf.md).
