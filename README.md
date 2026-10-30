# SUKI by Sushimanufaktúra – weboldal

Egyoldalas, statikus landing a győri SUKI bisztrónak (bao buns, sweet sushi, bowl). Készítette: **Stratos Webdesign**.

**Élő előnézet:** https://stratoswebdesign.github.io/suki/

## Felépítés
- `index.html` – teljes oldal: hero, menü (bao, bowl, snack, sweet sushi, bao menü), itallap, galéria, helyszín + térkép, JSON-LD (Restaurant schema)
- `assets/style.css` – minden stílus, színtokenek a `:root`-ban
- `assets/fonts/` – self-hostolt Google Fontok (Bagel Fat One, Bricolage Grotesque, Gochi Hand), nincs külső fontkérés (GDPR)
- `img/food/` – háttér nélküli, kivágott ételfotók (WebP, alfa csatorna)
- `img/photos/` – hangulatfotók 800 és 1600 px szélességben
- Build nincs, sima statikus fájlok → GitHub Pages / bármilyen tárhely

## Domain bekötése (GitHub Pages)
1. Repo → **Settings → Pages → Custom domain**: add meg a domaint (pl. `suki-gyor.hu`), mentés → a GitHub létrehozza a `CNAME` fájlt.
2. DNS a domainszolgáltatónál:
   - apex (`suki-gyor.hu`): **A** rekordok → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: **CNAME** → `stratoswebdesign.github.io`
3. Ha a tanúsítvány kész, pipáld be az **Enforce HTTPS**-t.
4. Cseréld a `https://stratoswebdesign.github.io/suki/` előtagot az új domainre: `index.html` (canonical, og:url, og:image, JSON-LD), `robots.txt`, `sitemap.xml`.

## Tartalom frissítése
- **Ár:** keresd az `index.html`-ben a `class="price"` elemeket.
- **Nyitvatartás:** `index.html` → `<table class="hours">` + a JSON-LD `openingHoursSpecification` része. A vasárnap még **egyeztetendő** (TODO komment jelöli).
- **Betűtípus-figyelmeztetés:** a Bagel Fat One display fontból hiányzik az `ő`, `ű` (és nagybetűs párjuk). Óriás címbe/gombba ne írj ilyen betűt, mert a böngésző másik fontra vált.

## Források
Menü és árak: az étterem nyomtatott étlapja és itallapja. Termékfotók: a SUKI Wolt-oldala. Hangulatfotók: az ügyféltől. Elérhetőségek: Google cégprofil és Facebook.
