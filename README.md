# Keno — mobile-first lottery landing

Test deployment for a Keno lottery landing page.

**Stack:** Static HTML · Vercel · GitHub.
**Style:** Dark Studio Tech (zinc-950 + electric cyan + JetBrains Mono).
**Audience:** CTO, Head of Mobile, Head of Analytics at mid-market Balkan iLottery operators.

## Live

After Vercel deploy, the page lives at: `https://test-keno.vercel.app/` (or your custom domain).

## What's on the page

- Hero with CSS phone mockup showing a Keno number grid + 60fps badge.
- 9-item engineering checklist as a terminal block.
- Mobile Performance Snapshot as CLI output (60fps · 1.18s first frame · 740MB · 7.2% battery · ±3% RUM delta · PWA PASS).
- 6 perf metric cards.
- 4-step integration timeline.
- Compliance pack (GLI-19, MGA B2B Critical Supply, WLA RG L1).
- 5-item FAQ accordion.
- Pricing block (12-18% revenue share).
- B2C-shadow video frame for player-perspective signal.
- Schema.org Product + FAQPage JSON-LD with `additionalProperty[]` on numeric performance claims.

## Local preview

Open `index.html` directly in a browser, or:

```bash
npx serve .
```

## Deploy

Pushed to `main` → Vercel auto-deploys via GitHub integration.

## Files

- `index.html` — the landing page (self-contained, no build step)
- `vercel.json` — security headers + cleanUrls
- `robots.txt` — allow AI crawlers (GPTBot, ClaudeBot, PerplexityBot) for citation-ready content
