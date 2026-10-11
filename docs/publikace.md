# Publikace

Web běží na **https://moped56.cz** přes GitHub Pages — větev `main`, složka
**`/ (root)`**. Každý push do `main` je za pár minut venku.

**Složka musí být `/ (root)`, ne `/docs`.** V `/docs` je tahle dokumentace,
ne web — kdyby se Pages nastavily na ni, zveřejní se místo webu tyhle poznámky.

## Doména

`moped56.cz` je u WEDOSu. V repozitáři je soubor `CNAME` s jediným řádkem
`moped56.cz`, u registrátora jsou A záznamy na IP adresy GitHub Pages a `www`
jako CNAME na `pesetasmasta.github.io`. V Settings → Pages je zapnuté
**Enforce HTTPS**.

## Vyhledávače

`robots.txt` a `sitemap.xml` leží v kořeni webu. Nový web bez odkazů zvenku
vyhledávače samy najdou pomalu, proto ho tam ohlásit ručně:

- **Google Search Console** — přidat doménu `moped56.cz` (ověření TXT záznamem
  u WEDOSu), odeslat `https://moped56.cz/sitemap.xml`, u úvodní stránky
  „Požádat o indexování“
- **Bing Webmaster Tools** — umí převzít web z Search Console; z Bingu bere
  výsledky i DuckDuckGo

Při větší změně obsahu přepsat `<lastmod>` v `sitemap.xml`.

## Webnode

Starý web `moped56.webnode.cz` se má zablokovat. Zatím chybí přihlašovací
údaje k účtu na Webnode.
