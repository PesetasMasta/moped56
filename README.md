# moped56

Web kapely MOPED 56 — jedna stránka, žádný build.

- `index.html` + `style.css` — celý web
- `promo.html` — zdroj promo materiálu pro pořadatele (A4, print CSS)
- `Moped56-promo.pdf` — vyrenderovaný materiál, na který web odkazuje
- `assets/cover.jpg` — obal alba *Ať se děje co děje*

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

Kapela to má doplnit, pak přegenerovat PDF a doplnit web:

- reference z let 2024 a 2025 — nejnovější jsou z roku 2023
- konkrétní monitorové mixy pro Vojtu a Patrika
- odkaz na živé video (pořadatel chce vidět publikum, ne klip)
- logo ve vektoru pro plakáty pořadatelů
- odkazy na streaming (Spotify, YouTube) — na webu zatím nejsou
- obal alba je jen 520×520 px, pro tisk je potřeba větší
