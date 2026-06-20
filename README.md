# Carmen's Asian Mini Market · 卡門亞洲小超市

Single-page bilingual (English / 繁體中文) website for **Carmen's Asian Mini Market Ltd**, a family-run South Asian & world grocery in Craig-y-Don, Llandudno.

- **Address:** 4–6 Victoria Buildings, Mostyn Avenue, Craig-y-Don, Llandudno LL30 1YU, Wales
- **Phone:** 01492 870630
- **Email:** Carmenli6@aol.com
- **Site:** carmensasiamarket.co.uk
- **Hours:** Mon–Sat 10:30–18:30 · Sun closed *(confirm before going live)*

## What's inside

A single self-contained `index.html` (no build step, no dependencies) with:

- Corner-shop "awning" branding, bilingual copy
- **86-line product catalogue** taken from the shop's real stock list, organised into 10 categories with a tap-to-filter bar
- Designed category image tiles per product (swap for real photos any time — see below)
- **Mail-order basket**: add items → `Mail order` tray → builds a pre-filled email to the shop (no backend needed)
- Google Maps embed, opening-hours table (auto-highlights today), contact + footer

## Project structure

```
.
├── index.html      # the whole site
├── vercel.json     # static config (clean URLs + basic headers)
├── images/         # optional: real product photos, named by stock code
├── .gitignore
└── README.md
```

## Deploy to Vercel

### Option A — GitHub auto-deploy (recommended)
1. Create a repo (e.g. `OTCoffice/carmens-asian-market`) and push these files.
2. In the Vercel dashboard → **New Project → Import** the repo.
3. Framework preset: **Other** (it's static). Click **Deploy**.
4. Every future `git push` to `main` redeploys automatically.

```bash
git init
git add .
git commit -m "Carmen's Asian Mini Market site"
git branch -M main
git remote add origin https://github.com/OTCoffice/carmens-asian-market.git
git push -u origin main
```

### Option B — Vercel CLI
```bash
npm i -g vercel
cd carmens-asian-market
vercel          # first run: log in + link project
vercel --prod   # publish to production
```

## Editing content

### Products / prices
Open `index.html` and edit the `PRODUCTS` array near the bottom (inside `<script>`).
Each item:

```js
{code:'F529A', brand:'Cirio', name:'Passata Classica', cn:'經典番茄碎醬',
 size:'540g', cat:'tin', ic:'🍅', price:null}
```

- `price: 1.49` shows a real price; `price: null` shows **"Price on order"** and is quoted by the shop on the mail order.
- `cat` must be one of: `spice, sauce, pickle, dal, rice, oil, tin, snack, drink, herb`.
- `ic` is the emoji shown on the tile.

### Real product photos
1. Add a photo to `images/`, named by stock code, e.g. `images/F529A.jpg`.
2. Add `img:'images/F529A.jpg'` to that product. The card and basket use the photo automatically.

### Opening hours / details
Search `index.html` for the `Opening hours` block, the address, phone and email — all plain HTML, edit in place.

---
© Carmen's Asian Mini Market Ltd · 4–6 Victoria Buildings, Mostyn Avenue, Llandudno LL30 1YU
