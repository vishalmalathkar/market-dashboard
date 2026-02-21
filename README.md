# 📈 India Market Pulse

A free, self-hosted, auto-refreshing dashboard showing live Indian financial market data.

## What it shows
| Data | Source | Delay |
|---|---|---|
| Gold (10g), Silver (1kg), Copper (1kg) in INR | Yahoo Finance (GC=F, SI=F, HG=F) | ~15 min |
| Petrol per litre (Hyderabad) | Static — update monthly | N/A |
| GIFT Nifty, Nifty 50, BSE Sensex | Yahoo Finance | ~15 min |
| Nifty Smallcap 100, Nifty Midcap 100 | Yahoo Finance | ~15 min |
| Positive & Negative Sectors (12 sectors) | Yahoo Finance NSE indices | ~15 min |

Auto-refreshes every **60 seconds**.

---

## 🚀 Deploy to GitHub Pages (Step-by-Step)

### Step 1 — Create a GitHub Account
Go to [github.com](https://github.com) and sign up (free).

### Step 2 — Create a New Repository
1. Click the **"+"** button (top right) → **New repository**
2. Name it: `market-dashboard` (or anything you like)
3. Set visibility to **Public**
4. Click **Create repository**

### Step 3 — Upload the Files
1. In your new repo, click **"Add file"** → **"Upload files"**
2. Upload these files:
   - `index.html`
   - `README.md`
   - `_config.yml`
3. Click **"Commit changes"**

### Step 4 — Enable GitHub Pages
1. Go to your repo → **Settings** tab
2. Scroll to **"Pages"** in the left sidebar
3. Under **"Branch"**, select `main` → `/ (root)` → click **Save**
4. Wait ~2 minutes

### Step 5 — Visit Your Live Site
Your site will be live at:
```
https://YOUR-USERNAME.github.io/market-dashboard/
```

---

## 🔧 Customization

### Change Petrol Price
Open `index.html`, find this line (~line 430):
```js
const PETROL_PRICE = 108.20;
```
Update the number and commit. Petrol prices change on the 1st of each month.

### Change City for Petrol
Update the label in the HTML:
```html
<div class="commodity-name">Petrol · Hyderabad</div>
```

### Change Refresh Interval
Find this line:
```js
const REFRESH_INTERVAL = 60; // seconds
```
Change `60` to any number (minimum recommended: 30 to avoid rate limiting).

---

## 📊 Data Sources (All Free)
- **Yahoo Finance** — `query1.finance.yahoo.com` (public, no API key needed)
- **CORS Proxy** — `corsproxy.io` (free, open source)
- **Petrol price** — Manually set from [IOCL website](https://iocl.com/petrol-diesel-price)

---

## ⚠️ Limitations
- Data is **~15 minutes delayed** (Yahoo Finance free tier)
- GIFT Nifty shows Nifty 50 spot as close approximation (exact GIFT SGX feed is paid)
- For real-time data, integrate a broker API: [Zerodha Kite](https://kite.trade/), [Angel One](https://smartapi.angelbroking.com/), or [Upstox](https://upstox.com/developer/api-documentation/)

---

## 💡 Tips
- Bookmark the GitHub Pages URL on your phone for quick access
- Works great as a browser homepage
- No server, no database, no monthly costs — just static HTML!
