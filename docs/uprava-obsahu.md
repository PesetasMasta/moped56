# Úprava obsahu

Web je jeden soubor `index.html` a jeden `style.css`. Žádný build, žádné npm.
Otevřít v editoru, změnit text, uložit, načíst v prohlížeči.

## Kde co je

| Co změnit | Kde |
|---|---|
| Claim pod názvem kapely | `index.html`, `<p class="claim">` |
| Obal alba | `assets/cover.jpg` (čtverec) |
| Datum vydání | `<p class="date">` v sekci `.release` |
| Popis alba | `<p class="meta">` tamtéž |
| Odkazy na poslech a prodej | `<div class="links">` tamtéž |
| Text o kapele | sekce `#kapela`, `<div class="prose">` |
| Sestava | `<ul class="lineup">` |
| Diskografie | sekce `#diskografie`, `<ol class="records">` |
| Info pro pořadatele | sekce `#poradatele`, `<dl class="specs">` |
| Kontakt | sekce `#booking`, `<ul class="contact">` |

## Přidání desky do diskografie

Nový řádek na začátek seznamu `.records`:

```html
<li><span class="rec-year">2028</span> <span class="rec-name">Název desky</span></li>
```

Když je deska ke koupi na Supraphonline, obalit název odkazem:

```html
<span class="rec-name"><a href="https://www.supraphonline.cz/album/..." rel="noopener">Název desky</a></span>
```

První řádek seznamu se automaticky vybarví červeně jako nejnovější deska —
nová deska proto patří nahoru.

## Změna textu i v PDF

Sestava, technické požadavky a diskografie jsou na dvou místech: na webu
(`index.html`) a v promo materiálu (`promo.html`). Když se mění jedno, projít
i druhé a přegenerovat PDF — viz [promo-pdf.md](promo-pdf.md).

## Diakritika

Text psát normálně s háčky a čárkami, soubory jsou v UTF-8. Pozor jen na
velké nadpisy přes víc řádků — viz [design.md](design.md#háčky-a-řádkování).
