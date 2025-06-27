# ADR-001: Val av teknikstack för ny webbplats

## Status

Accepted

## Datum

2025-06-27

## Kontext

Vi bygger en ny extern webbplats för Mira. Webbplatsen ska vara:

- **Lättviktig och snabb**
- **Enkel att bygga och deploya**
- **Lätt att redigera via grafiskt gränssnitt**
- **Versionshanterad i Git**
- **Underhållsvänlig för både utvecklare och redaktörer**

Målet är att ha en modern teknikstack som inte kräver backend, CMS-installation eller databashantering, men ändå ger möjlighet till skräddarsydd design och innehållshantering.

## Beslut

### 🧱 Static Site Generator: **Eleventy (11ty)**

Vi använder [Eleventy](https://www.11ty.dev/) för att generera statiska sidor från markdown och templates:

- Enkel och snabb att köra lokalt
- Flexibel och ramverksfri
- Stöd för Liquid, Nunjucks, Markdown m.m.
- Passar utmärkt med ett Git-baserat CMS

### ✍️ CMS: **Decap CMS**

[Decap CMS](https://decapcms.org/) (tidigare Netlify CMS) används som innehållshanteringssystem:

- Redaktörer kan logga in i ett webbaserat gränssnitt och redigera innehåll
- Innehållet versioneras direkt i Git (via commits)
- Kräver ingen backend/server – allt hanteras via GitHub
- Kan köras lokalt med `npx netlify-cms-proxy-server` och `local_backend: true`

### 🎨 CSS: **Tailwind CSS**

Vi använder [Tailwind CSS](https://tailwindcss.com/) för styling:

- Utility-first-metod ger snabb och konsekvent design
- Enkel att anpassa och skala
- Fungerar bra med Eleventy

> ❌ Vi använder **inte** Bootstrap. Anledningar:
> - Bootstrap 3 är föråldrat
> - Bootstrap i allmänhet är mindre flexibel och har ett tungt legacy
> - Tailwind ger bättre kontroll och modernare workflow

### ✨ JS: **Alpine.js**

[Alpine.js](https://alpinejs.dev/) används för lätt interaktivitet (t.ex. mobilmeny, toggle-komponenter):

- Lättviktigt
- Deklarativt och enkelt att förstå
- Fungerar bra med statiska sidor och kräver ingen bygg-pipeline

### 🔎 Sökfunktion: **Client-side Fuse.js + JSON-index**

Vi kommer använda [Fuse.js](https://fusejs.io/) som klientbaserad sökmotor:

- Vid build genereras ett `search-index.json` med relevant innehåll
- Fuse.js laddar indexet och gör fuzzy search i webbläsaren
- Ingen server krävs
- Kan kompletteras med [pagefind](https://pagefind.app/) i framtiden för bättre prestanda

### 🛠 Lokal utveckling

- Byggs via `npm run dev` (Eleventy med watch + Tailwind CLI)
- CMS körs via `npx netlify-cms-proxy-server`
- GitHub används som source of truth
- Redigeringar via Decap CMS genererar commits i main-branchen
- Deployment via GitHub Pages eller annan CI/CD

### 🧪 Övriga verktyg

- Vi använder `postcss` för Tailwind och eventuell framtida CSS-transformering
- All konfiguration ligger i Git (t.ex. `config.yml` för Decap)

## Avvisade alternativ

| Alternativ | Skäl till avvisning |
|-----------|---------------------|
| WordPress  | För tungt, kräver backend |
| Sanity, Contentful | Ej Git-baserade, dyrare, mer komplexa |
| Bootstrap | Legacy, tungt, låg flexibilitet |
| Next.js | För mycket JS och runtime för enkel sajt |
| Lunr.js för sök | Tyngre än Fuse, sämre fuzzy search |
| Serverbaserad sök | Onödigt för vår typ av innehåll |

## Konsekvenser

- Enkel hantering, låg tröskel för redaktörer
- Extremt låg driftkostnad
- Inga databaser eller backend – allt sker via Git och byggsteg
- Utvecklare behöver kunna hantera Node.js, Git och Tailwind CLI
- Sök fungerar även offline, men kräver manuell indexgenerering vid build

## Nästa steg

- Skapa README med instruktioner för:
  - Setup av Node och npm (gärna via `winget`)
  - Kommandon för `npm install`, `npm run dev`, `npx netlify-cms-proxy-server`
- Dokumentera CMS-konfiguration och innehållsstruktur
- Testa deploy till GitHub Pages
