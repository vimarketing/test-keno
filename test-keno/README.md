# Lotteries Studio — multi-page static site

Holding canonical: `https://keno-test.netlify.app/`
Brand placeholder: **Lotteries Studio** (pending naming sprint)
Email placeholder: **hello@lotteries.studio**

---

## What this is

A 7-page static HTML marketing site for the studio:

- `/` — homepage (Style C "Warm Editorial Balkan", multi-product overview)
- `/products/keno/` — Keno (Style B "Dark Studio Tech", existing test-keno content ported)
- `/products/fortuna/` — Fortuna jackpot draw (Style C, compliance-focused)
- `/products/bingo-filipano/` — Bingo Filipano 4-week integration (Style C)
- `/products/bingo/` — Bingo aggregator-channel (Style C)
- `/about/` — studio overview, credentials, principles (Style C)
- `/contact/` — contact form + direct email (Style C)

No build step. Pure HTML/CSS, schema.org JSON-LD per page, OG/Twitter cards, multi-locale-ready.

---

## How to deploy (drag-and-drop to Netlify)

This is the manual deploy path — no GitHub integration needed.

### 1. Sign in to Netlify
Go to https://app.netlify.com/ and sign in.

### 2. Open the deploys tab
- If this is the **first deploy:** click **"Add new site" → "Deploy manually"** on the dashboard.
- If you're **redeploying** the existing test-keno project: click into the site → **Deploys** tab → scroll to the drag-and-drop area at the bottom (labelled "Need to update your site? Drag and drop your site output folder here").

### 3. Drag the entire `lotteries-studio-site/` folder
Select the **whole folder** in your file explorer (the one that contains `index.html`, `products/`, `about/`, `contact/`, `sitemap.xml`, etc.) and **drag it onto the Netlify deploy area**.

> ⚠️ Drag the **folder**, not its contents. Netlify reads `netlify.toml` from the folder root.

### 4. Wait for the deploy preview
~30-60 seconds. Netlify shows a green "Published" banner with a temporary URL like `https://random-name-123abc.netlify.app/`.

### 5. (Optional) Rename to keno-test
- Site settings → **Site information** → **Change site name** → enter `keno-test`.
- Public URL becomes `https://keno-test.netlify.app/` — matches the holding canonical baked into all pages.

### 6. Verify the deploy
Open these URLs in order and confirm each loads without 404:

```
https://keno-test.netlify.app/
https://keno-test.netlify.app/products/keno/
https://keno-test.netlify.app/products/fortuna/
https://keno-test.netlify.app/products/bingo-filipano/
https://keno-test.netlify.app/products/bingo/
https://keno-test.netlify.app/about/
https://keno-test.netlify.app/contact/
https://keno-test.netlify.app/sitemap.xml
https://keno-test.netlify.app/llms.txt
https://keno-test.netlify.app/robots.txt
```

### 7. (Optional) Submit sitemap to Google Search Console
- Property → Sitemaps → Add new sitemap → `sitemap.xml` → Submit.

---

## File map

```
lotteries-studio-site/
├── index.html                       Homepage (Style C, multi-product overview)
├── netlify.toml                     Headers, redirects, 404 handling
├── sitemap.xml                      All 7 URLs
├── robots.txt                       Allows AI crawlers + Cloudflare Content-Signal
├── llms.txt                         LLM-friendly summary (llmstxt.org spec)
├── manifest.webmanifest             PWA manifest
├── logo.svg                         Brand mark
├── og-image.png                     1200×630 OG card (228KB)
├── og-image.svg                     OG card source (vector)
├── apple-touch-icon.png             180×180 iOS home-screen icon
├── icon-192.png                     PWA icon
├── icon-512.png                     PWA icon
├── icon-maskable-512.png            PWA maskable icon (Android adaptive)
├── README.md                        This file
│
├── products/
│   ├── keno/index.html              Style B "Dark Studio Tech" (zinc-950 + cyan)
│   ├── fortuna/index.html           Style C, compliance-ready jackpot draw
│   ├── bingo-filipano/index.html    Style C, 4-week integration narrative
│   └── bingo/index.html              Style C, aggregator-channel content
│
├── about/index.html                 Studio overview, credentials, principles
└── contact/index.html               Contact form + direct email
```

---

## Brand-name TODO (post-naming-sprint)

When the naming sprint finalises a real brand name (replacing "Lotteries Studio") and a real domain (replacing `keno-test.netlify.app`), there is a **rename checklist** that has to run across all files. The string occurrences are:

| Placeholder | What to replace with |
|---|---|
| `Lotteries Studio` | Final studio name |
| `lotteries.studio` | Final domain (in `hello@…` and OG metadata) |
| `keno-test.netlify.app` | Final domain |
| `https://keno-test.netlify.app` | `https://<final-domain>` |

Files that need to be updated (every URL/email reference):

- All 7 `index.html` files (canonical, OG, Twitter, JSON-LD `@id` graph references, footer text)
- `sitemap.xml` (all 7 `<loc>` URLs)
- `robots.txt` (Sitemap directive)
- `llms.txt` (all URLs + brand name in title and citation-ready facts)
- `netlify.toml` (no URL references — safe)
- `manifest.webmanifest` (name, short_name, description)
- `README.md` (this file — verification URLs)

A find-and-replace across the deploy folder is the fastest way; verify each `index.html` has all occurrences updated before redeploying.

---

## Style tier reference

- **Style B "Dark Studio Tech"** (zinc-950 + electric cyan #22D3EE + JetBrains Mono): Keno only. Locked per DL-0015 because Keno's audience skews technical (CTO, integration engineer) and the high-contrast dark palette signals engineering-density.
- **Style C "Warm Editorial Balkan"** (cream #F5F0E6 + deep navy #0C2A4A + terracotta #C2563A + Fraunces serif + Inter): All other pages. Editorial-restraint visual signals trust to compliance-and-commercial decision units.

When the brand-name + visual-system finalises in PHASE 1, both styles will roll into a single locked design system. Until then, this two-tier split is by design.

---

## Last updated

2026-04-29 — multi-page deploy with all 7 pages, full SEO/OG/JSON-LD stack, AI-crawler-friendly robots+llms, PWA manifest.
