# Carmen's Asian Mini Market Ltd · 卡門亞洲小超市

Single-page bilingual (English / 繁體中文) website for **Carmen's Asian Mini Market Ltd**, a family-run Asian & South Asian grocery in Craig-y-Don, Llandudno.

- **Address:** 4–6 Victoria Buildings, Mostyn Avenue, Craig-y-Don, Llandudno LL30 1YU, Wales
- **Phone:** 01492 870630
- **Email:** Carmenli6@aol.com
- **Hours:** Mon–Sat 10:30–18:30 · Sunday 11:00–18:00 (open 7 days)
- **Established:** 2006

## What's inside

A single self-contained `index.html` (no build step, no dependencies):

- Corner-shop "awning" branding, bilingual copy, high-contrast palette
- **136-line product catalogue** from the shop's real stock lists (54 price-marked), tap-to-filter by type
- Mail-order basket → builds a pre-filled email to the shop (no backend)
- Two-step payment: **① email order → ② PayPal or Santander bank transfer**
- Google Maps embed, opening-hours table (auto-highlights today), contact + footer

## Files

```
index.html     # the whole site (this is what gets served)
vercel.json    # static config (clean URLs + headers)
images/        # optional real photos, named by stock code
README.md
GO-LIVE.md     # step-by-step deploy guide
```

## Deploy (GitHub → Vercel)

1. This repo's **`index.html`** is the live site. To update it, upload a new `index.html` to overwrite the old one (Add file → Upload files → Commit).
2. In Vercel: **New Project → Import** this repo → Framework **Other** → **Deploy**.
3. Every commit to `main` redeploys automatically.

See `GO-LIVE.md` for the full walkthrough (incl. custom subdomain + payment details).

## Editing

- **Products / prices:** edit the `PRODUCTS` array in `index.html`. `price: 1.49` shows a price; `price: null` shows "Price on order".
- **Real photos:** drop an image in `images/` named by stock code (e.g. `LKK124.jpg`) and add `img:'images/LKK124.jpg'` to that product.
- **Hours / address:** search `index.html` for `Opening hours` / `4–6 Victoria` and edit in place.

## Payment

- **PayPal:** carmenli6@aol.com (amount pre-filled from priced items)
- **Bank (Santander):** Mrs Y M Boddis · Sort code 09-01-29 · Account 77594857

---
© 2026 Carmen's Asian Mini Market Ltd · 4–6 Victoria Buildings, Mostyn Avenue, Llandudno LL30 1YU
