# Promo materiál pro pořadatele

`Moped56-promo.pdf` je to, co si pořadatel stáhne z webu. Nevzniká ručně —
generuje se z `promo.html`, takže se dá kdykoli upravit a přegenerovat.

## Přegenerování

```bash
cd ~/dev/moped56
"/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --headless --disable-gpu --no-pdf-header-footer --virtual-time-budget=8000 \
  --print-to-pdf="$PWD/Moped56-promo.pdf" "file://$PWD/promo.html"
```

Chrome funguje stejně, jen jiná cesta k binárce.

**Výsledek musí mít 2 strany.** Kontrola:

```bash
pdfinfo Moped56-promo.pdf | grep Pages
```

Když jich vyjde víc, něco na první straně přeteklo — obvykle přibyl text do
bloku "Kde jsme hráli" nebo do praktického infa. Řešení je zkrátit text, ne
zmenšovat písmo; strana je záměrně plná až po patičku s kontaktem.

"Kde jsme hráli" má místo na **čtyři řádky**, jeden řádek na rok, nejnovější
nahoře, akce v řádku taky od nejnovější. S novým rokem sloučit nebo vypustit
nejstarší řádek (proto 2022–23; řádek bez roku, Klub Kotelna a Rockové
Třtěnice, už vypadl).

`--virtual-time-budget=8000` dává prohlížeči čas načíst písmo Oswald z Google
Fonts. Bez toho se PDF vysází systémovým fontem a vypadá jinak než web.

## Co se v PDF liší od původního materiálu

Původní `Moped56_promo_pro_poradatele.pdf` obsahoval interní pracovní poznámky.
Ty ve verzi na webu nejsou:

- žlutý rámeček "OVĚŘIT S KAPELOU" (dotazy na odposlechy a mikrofony na bicí)
- celá stránka "CO JEŠTĚ DODAT, NEŽ TO POŠLETE POŘADATELŮM"
- poznámka o souhlasu s použitím fotky
- dvě prázdná místa `[doplnit]` u monitorových mixů — nahrazena větou
  *"Mixy pro Vojtu Hubingera a Patrika Kořínka doladíme se zvukařem na místě."*

Všechno ostatní je doslovně převzaté. Mix 2 pro Jana Jaška zůstal, jak byl.

## Co do materiálu chybí

Tohle si musí doplnit kapela, pak stačí upravit `promo.html` a přegenerovat:

- **konkrétní monitorové mixy** pro Vojtu a Patrika
- **logo ve vektoru** pro plakáty pořadatelů
