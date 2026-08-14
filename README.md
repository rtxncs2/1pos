# 🛒 ShopDesk POS

A lightweight, fully offline Point of Sale system built as a single HTML file. No server, no dependencies to install, no database setup — just open `pos-app.html` in any browser and start selling.

---

## ✨ Features

### 📦 Inventory Management
- Add, edit, and delete products with SKU, name, category, price, stock quantity, and low-stock threshold
- Visual stock status badges — **In Stock**, **Low Stock**, **Out of Stock**
- Search products by name, SKU, or category
- Import inventory from a JSON file or export current stock to JSON for backup

### 🛒 Billing / POS
- Browse products in a card grid with category filter and search
- Click **Add to Cart** to add items; adjust quantities with `+` / `−` or type directly
- Per-sale discount (flat ₹ or percentage), GST %, customer name, and payment method
- Stock is automatically deducted on sale completion

### 🧾 Invoice & Receipt
- Thermal-style receipt generated after every sale
- **Print** — sends a clean, styled invoice to your printer
- **Save PDF** — downloads the invoice as a PDF (e.g. `INV-0001.pdf`)
- Re-open any past receipt from the Summary tab

### ↩ Sales Returns
- Process returns by invoice reference and SKU
- Stock is automatically restocked on return
- Reason tracking: Defective, Wrong item, Customer changed mind, Damaged in transit, Other

### 📊 Stock & Sales Summary
- Dashboard stats: Total Revenue, Total Sales, GST Collected, Discounts Given, Total Products, Returns Processed
- Date range filter for all stats and the sales table
- Low stock alert table
- Export sales history as CSV

---

## 🚀 Getting Started

No installation required.

1. Download `pos-app.html`
2. Open it in any modern browser (Chrome, Firefox, Edge)
3. Start adding products in the **Inventory** tab
4. Switch to **Billing** to make sales

To load the sample inventory of 50 electronics products:

1. Download `shopdesk-data.json`
2. Go to the **Inventory** tab → click **⬆ Import JSON**
3. Select the file

---

## 💾 Data Storage

All data is stored in **`localStorage`** in your browser — it persists across page refreshes automatically.

| Action | Effect on localStorage | Effect on JSON file |
|---|---|---|
| Add / Edit / Delete item | ✅ Updated instantly | ❌ Not affected |
| Complete a sale | ✅ Updated instantly | ❌ Not affected |
| Export JSON | No change | ✅ Snapshot written to disk |
| Import JSON | ✅ Replaced with file contents | No change |

> **Tip:** Export a JSON backup regularly to avoid data loss if browser storage is cleared.

---

## 📁 File Structure

```
├── pos-app.html          # The entire application (single file)
└── shopdesk-data.json    # Sample inventory — 50 electronics products
```

---

## 🖨 Print & PDF Notes

- **Print** opens a clean invoice page and triggers the browser print dialog. If it's blocked (e.g. in certain sandboxed environments), it falls back to an iframe-based print.
- **Save PDF** uses [jsPDF](https://github.com/parallax/jsPDF) + [html2canvas](https://github.com/niklasvh/html2canvas), loaded on demand from cdnjs. Requires an internet connection on first use.

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| UI | Vanilla HTML, CSS, JavaScript |
| Fonts | Inter + JetBrains Mono (Google Fonts) |
| Storage | Browser `localStorage` |
| PDF | jsPDF + html2canvas (CDN, on demand) |
| Packaging | Single `.html` file — zero build step |

---

## 📋 Roadmap / Ideas

- [ ] Multi-currency support
- [ ] Barcode scanner input support
- [ ] Daily sales chart in Summary tab
- [ ] Cloud sync via a backend API
- [ ] PWA support for offline-first mobile use
- [ ] Multiple user / cashier profiles

---

## 📄 License

MIT — free to use, modify, and distribute.

---

> Built with ❤ as a hobbyist project. Contributions and suggestions welcome.
