# Heimish Discount — Website

Static site for heimishdiscount.com. Pure HTML + Tailwind (via CDN) — no build step.

## Structure

```
website/
├── index.html                       # Landing page → https://heimishdiscount.com
├── privacy-policy/index.html        # → https://heimishdiscount.com/privacy-policy
├── terms-and-conditions/index.html  # → https://heimishdiscount.com/terms-and-conditions
├── admin/
│   ├── login.html                   # Admin login (demo — any creds work)
│   └── dashboard.html               # Admin CRM: Overview, Rides, Riders, Drivers, Earnings, Verification, Promo Codes
└── README.md
```

Folder-based URLs (no `.html` extension) resolve correctly on GitHub Pages, Vercel, and Netlify without rewrite rules.

## Deploy to GitHub Pages (fastest path)

```bash
cd "C:/Users/chaim/Desktop/heimish discount app/website"
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/<your-username>/heimish-website.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Source: `main` / `(root)`**. Site goes live at `https://<your-username>.github.io/heimish-website/`.

For a custom domain (heimishdiscount.com), add a `CNAME` file containing the domain and configure DNS.

## Deploy to Vercel / Netlify (drag-and-drop)

Either platform accepts the `website/` folder directly — no config needed. Vercel gives you a free `*.vercel.app` URL immediately.

## Replace before production

- App Store / Play Store links in `index.html` (currently `#`)
- Admin login is **demo only** — wire up Supabase Auth or similar before going live
- Dashboard data is hard-coded — connect to Supabase
- Contact emails in `privacy.html` and `terms.html`
