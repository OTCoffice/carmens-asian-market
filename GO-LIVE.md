# Carmen's Asian Mini Market Ltd — 上線操作單 / Go-live Guide

部署檔:`carmens-asian-market.zip`(解壓後有 `index.html`、`vercel.json`、`README.md`、`.gitignore`、`images/`)
最簡單路徑:**GitHub 網頁上傳 → Vercel**(全程瀏覽器,不用裝 git)。

---

## 步驟 A — 上傳到 GitHub

1. 解壓 `carmens-asian-market.zip`。
2. 打開你的 repo：`https://github.com/OTCoffice/carmens-asian-market`
3. 點 **Add file → Upload files**(或首頁藍字 "uploading an existing file")。
4. 把這些**全部拖進去**：`index.html`、`vercel.json`、`README.md`、`.gitignore`、`images/` 資料夾。
5. 下方綠色 **Commit changes** 按下去。完成。

> 之後要改內容：同樣 Add file → Upload files 覆蓋 `index.html`，Vercel 會自動重新部署。

---

## 步驟 B — 在 Vercel 部署

1. 登入 `https://vercel.com`（用 GitHub 帳號登入最快）。
2. **Add New → Project → Import** 選 `OTCoffice/carmens-asian-market`。
3. Framework Preset 選 **Other**（這是靜態站）→ **Deploy**。
4. 約 30 秒，拿到網址 `carmens-asian-market.vercel.app`。
5. 打開測一遍：分類篩選、加入購物籃、① email 下單、② PayPal / 銀行轉帳、Google 地圖。

到這裡網站已經「活」在 vercel.app 上了。

---

## 步驟 C — 網域（重要，先看清楚）

`carmensasiamarket.co.uk` 是店家**現有官網**（用 WebsitesForFree 平台），**不要**把主網域指過來，否則會把現有店面換掉。

要讓新站掛在自家網域下，用**子網域**：

1. Vercel 專案 → **Settings → Domains** → 輸入 `order.carmensasiamarket.co.uk`（名稱可自訂，如 zh. / shop.）。
2. Vercel 會顯示一筆 **CNAME** 目標（通常 `cname.vercel-dns.com`）。
3. 到**管這個網域 DNS 的後台**新增：類型 CNAME、名稱 `order`、值 = Vercel 顯示的目標。
4. 生效後 `https://order.carmensasiamarket.co.uk` 自動配 HTTPS、上線。
5. （選用）在舊官網選單放一個連結指向這個子網域。

> 沒有 DNS 權限就先用 `carmens-asian-market.vercel.app`，完全能正常營運。

---

## 付款方式（已設定好）

- **PayPal**：收款 email `carmenli6@aol.com`，客人點 PayPal 會帶入已標價金額。
- **銀行轉帳 (Santander)**：Mrs Y M Boddis／Sort code 09-01-29／Account 77594857。
- 流程：客人 ① email 下單 → 店家確認庫存・未標價品項・運費・總額 → 客人 ② 付款。

---

## 之後要自己改的小地方

- **商品 / 價格**：`index.html` 內 `PRODUCTS` 陣列。`price: 數字` 顯示價格；`price: null` 顯示「Price on order」。
- **真實照片**：把圖丟進 `images/`，以貨號命名（如 `LKK124.jpg`），再到該品項加 `img:'images/LKK124.jpg'`。
- **營業時間 / 地址 / 電話**：搜尋 `Opening hours` / `4–6 Victoria` 直接改。

---

## 待你日後確認

- 冬蔭功（LKK673）暫定 **£1.50**（到貨單上另有 £1.25）。
- 小老闆海苔原味（TAK101）暫定規格 **32g**。
- 新加坡分類目前無貨，顯示「Coming soon」，有進貨清單再補。
