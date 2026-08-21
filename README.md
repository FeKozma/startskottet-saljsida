# Startskottet — säljsida för nya funktioner

En fristående, enkel landningssida som presenterar fyra kommande flikar i
[Startskottet](../startskottet) (volontärer, uppgifter, mål, utvärdering) för
lopparrangörer inom föreningen. Ren statisk HTML/CSS, inget byggsteg, inget
ramverk.

De fyra funktionerna finns just nu i grenen `feature/volunteers-tab-mock-interactivity`
i huvudrepot och är inte ännu sammanslagna till `master`. Den här sidan är en
förhandstitt/säljande presentation, inte den körande appen.

## Köra lokalt (utan Docker)

Vilken statisk filserver som helst funkar, t.ex.:
```bash
npx serve .
```

## Köra med Docker (så som den är tänkt att driftas)
```bash
docker compose up -d --build
# → http://localhost:8080
```

## Struktur
- `index.html` — hela sidan, en fil
- `css/style.css` — all styling
- `assets/logo-emblem.svg`, `assets/favicon.svg` — Startskottets logotyp
- `Dockerfile` / `docker-compose.yml` / `nginx.conf` — nginx-baserad statisk
  driftsättning

## Om skärmbilderna
Panelerna som visar varje flik är handbyggda HTML/CSS-attrapper som återger
den riktiga gränssnittsstrukturen och färgkodningen (samma flikfärger som i
appen: teal/röd/grön/slate) — inte råa skärmdumpar. Det verkliga
utvecklingsläget har testdata och trasiga integrations-varningar som inte
passar en säljande sida. Vill du byta ut dem mot riktiga skärmdumpar när
funktionerna har skarp data: lägg PNG-filer i `assets/screenshots/` och byt ut
`.mock-window`-blocket i `index.html` mot en `<img>`.
