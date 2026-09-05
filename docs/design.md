# Vizuální styl

Všechno je odvozené z obalu alba *Ať se děje co děje*: černá, jedna červená,
špinavě bílá, těžké úzké verzálky. Žádné přechody, žádné stíny, žádné
zaoblené rohy — plakát, ne firemní web.

## Barvy

Definované jako CSS proměnné na začátku `style.css`:

| Proměnná | Hodnota | Kde |
|---|---|---|
| `--ink` | `#101010` | pozadí stránky |
| `--ink-soft` | `#1b1b1b` | řádky sestavy |
| `--paper` | `#f0ece4` | text |
| `--paper-dim` | `#9c968b` | doplňkový text, popisky |
| `--red` | `#c1272d` | akcent z obalu |
| `--red-hot` | `#e5372c` | odkazy a hover |

Změna barvy se dělá na jednom místě nahoře, ne po souboru.

## Písmo

Nadpisy **Oswald** (700 a 500) z Google Fonts, text systémový sans-serif.
Oswald je úzký grotesk s plnou podporou české diakritiky.

Web font se načítá z Googlu. Když stránka běží bez internetu, nadpisy spadnou
na `Arial Narrow` a rozpadne se jen typografie, ne rozvržení.

## Zrno

Přes celou stránku leží vrstva šumu (`body::after`, SVG `feTurbulence`,
krytí 5 %). Bez ní vypadá plochá černá jako prezentace. Je `pointer-events:
none`, takže nepřekáží klikání.

## Háčky a řádkování

**Na tohle si dát pozor.** Velké verzálky s háčky potřebují víc místa mezi
řádky, než by se u plakátové typografie čekalo.

Název alba `AŤ SE DĚJE / CO DĚJE` měl původně `line-height: 0.98`. Háček nad
Ě z druhého řádku vyjel nahoru do prvního a mezi „SE" a „DĚJE" se objevila
čárka — vypadalo to jako `AŤ SE, DĚJE`. Testováno i na 1.06, 1.10 a 1.16, kde
byl artefakt pořád vidět. Čisté je to od **1.22**, což je současná hodnota.

Pravidlo: u víceřádkového nadpisu z verzálek s diakritikou nejít pod
`line-height: 1.2` a vždycky se podívat na výsledek, ne jen na kód.

## Šířky

Obsah je omezený na `60rem` a je jednosloupcový. Jediný zlom je na `46rem`,
kde se blok s obalem alba rozdělí na dva sloupce a technické info dostane
popisky vlevo. Web byl kontrolovaný na 1280 px a na 500 px.
