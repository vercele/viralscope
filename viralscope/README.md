# ViralScope AI — Deployment na Vercel

## Šta je ovo?
Kompletna web aplikacija za istraživanje viral short-form video sadržaja.
Bezbedno čuva Anthropic API ključ na serveru (ne u browseru).

## Deploy za 5 minuta

### Korak 1 — Napravi Vercel nalog
Idi na https://vercel.com i registruj se (besplatno).

### Korak 2 — Instaliraj Vercel CLI
```bash
npm install -g vercel
```

### Korak 3 — Deploy
```bash
cd viralscope
vercel
```
Prati uputstva — odaberi "No" za sve pitanja osim "Override settings? No".

### Korak 4 — Dodaj API ključ
1. Idi na https://vercel.com/dashboard
2. Otvori tvoj projekat → Settings → Environment Variables
3. Dodaj:
   - Name: `ANTHROPIC_API_KEY`
   - Value: tvoj API ključ (sa https://console.anthropic.com)
4. Klikni Save

### Korak 5 — Redeploy
```bash
vercel --prod
```

Gotovo! Aplikacija je živa na `https://tvoj-projekat.vercel.app`

## Alternativa: GitHub + Vercel (bez CLI)
1. Napravi GitHub repo i uploaduj fajlove
2. Na Vercel.com: "Import Project" → poveži GitHub repo
3. Dodaj `ANTHROPIC_API_KEY` u Environment Variables
4. Klikni Deploy

## Struktura projekta
```
viralscope/
├── api/
│   └── claude.js      ← serverless funkcija (čuva API ključ)
├── public/
│   └── index.html     ← kompletna aplikacija
└── vercel.json        ← konfiguracija
```
