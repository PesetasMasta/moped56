# Publikace

Repozitář je zatím **privátní**, aby si to kapela mohla projít dřív než kdokoli
jiný. Dokud se nepřepne na public, web nikde neběží — funguje jen lokálně
otevřením `index.html` v prohlížeči.

## Zveřejnění

1. GitHub → Settings → General → Danger Zone → **Change visibility** → public
2. Settings → **Pages** → Source: *Deploy from a branch* → větev `main`,
   složka **`/ (root)`**
3. Za pár minut web běží na `https://pesetasmasta.github.io/moped56/`

**Složka musí být `/ (root)`, ne `/docs`.** V `/docs` je tahle dokumentace,
ne web — kdyby se Pages nastavily na ni, zveřejní se místo webu tyhle poznámky.

## Vlastní doména

`pesetasmasta.github.io/moped56/` je adresa, která v mailu pořadateli působí
jako hobby projekt. `moped56.cz` je u WEDOSu kolem 150 Kč/rok.

Postup, až se kapela rozhodne:

1. registrace domény — držet by ji měla kapela, ne kdokoli, kdo web dělal
2. do repozitáře přidat soubor `CNAME` s jediným řádkem `moped56.cz`
3. u registrátora nastavit A záznamy na IP adresy GitHub Pages a `www` jako
   CNAME na `pesetasmasta.github.io`
4. v Settings → Pages zapnout **Enforce HTTPS**, jakmile se certifikát vystaví

## Webnode

Starý web `moped56.webnode.cz` zůstal nedotčený. Až bude nový web venku, jsou
to dvě adresy pro jednu kapelu a ta starší je neaktuální — rozhodnout, jestli
na nový web jen odkázat, přesměrovat, nebo starý zrušit.
