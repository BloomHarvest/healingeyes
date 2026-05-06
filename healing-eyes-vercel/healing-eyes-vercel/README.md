# Healing Eyes — Static Site

Production-ready static HTML site for Healing Eyes (Samantha McGee — iridologist & sclerologist).

## Architecture

- **Front-end:** Static HTML hosted on Vercel
- **Back-end:** GoHighLevel (checkouts, calendars, courses, emails, CRM, AI agent)
- **Domain:** `healingeyesholistic.com` (registered at GoDaddy, DNS to Vercel on launch June 11)

## Pages

| Route | File | Purpose |
|---|---|---|
| `/` | `index.html` | Home page — full product ladder + brand story |
| `/foundation` | `foundation-course.html` | Foundation Course sales page ($347) |
| `/academy` | `academy.html` | Academy application page (3 tracks: $1,997 / $3,500 / $5,000) |

## File Structure

```
healing-eyes-vercel/
├── index.html
├── foundation-course.html
├── academy.html
├── vercel.json          # Clean URL routing + asset caching headers
├── assets/              # Images (logos, iris, mockups)
│   ├── logo-navy.png
│   ├── logo-white.png
│   ├── iris-hero.jpg
│   ├── iris-bio-bg.jpg
│   ├── foundation-hero.jpg
│   ├── component-1-videos.jpg
│   ├── component-2-pdf.jpg
│   ├── component-3-library.jpg
│   └── component-4-workbook.jpg
└── README.md
```

## Tech Stack

- **HTML5 + CSS3** (no framework, no build step)
- **Google Fonts:** Bebas Neue + Cormorant Garamond + Inter
- **No JavaScript dependencies** beyond inline FAQ accordion logic
- **Mobile-first responsive** with breakpoints at 700px (tablet) and 1024px (desktop)

## Brand System

- **Cream:** `#FBF6E9`
- **Navy:** `#1A2B5C`
- **Sage:** `#7BB99F` (primary CTAs)
- **Gold:** `#B8935A` (luxury accent)
- **Rust:** `#B85C3A` (italic accent)

## Pending Wire-up

All buy/book/apply buttons currently use `#` placeholder URLs. Before going live with real traffic, replace these with real GHL checkout/booking URLs:

### index.html
- Eye Type Guide ($27) → GHL Stripe checkout
- Body Systems Library ($47) → GHL Stripe checkout
- Mini Iris Snapshot ($67) → GHL booking form
- Video Analysis ($197) → GHL booking form
- Live 1-on-1 Session ($247) → GHL calendar
- Foundation Course ($347) → links to `/foundation`
- Academy → links to `/academy`

### foundation-course.html
- ENROLL NOW — $347 (multiple instances) → GHL Stripe checkout
- Academy bridge link → `/academy`

### academy.html
- Apply — $1,997 → GHL application form
- Apply — $3,500 → GHL application form
- Apply — $5,000 → GHL application form
- Apply for Cohort 1 (Hero + Final CTA) → GHL application form

### Footer (all 3 pages)
- Reach Samantha on TikTok → real TikTok URL
- Legal → `/legal` page (to be created at launch)

## Deployment

### First-Time Vercel Setup

1. Push this folder to your GitHub repo
2. Go to Vercel dashboard → New Project → Import Git Repository
3. Select your repo
4. Framework Preset: **Other** (Vercel auto-detects static HTML)
5. Click **Deploy**

### Updates

```bash
# After making changes locally
git add .
git commit -m "describe what changed"
git push origin main
```

Vercel auto-deploys on every push to `main`.

### Custom Domain (Pre-Launch)

1. Vercel Project → Settings → Domains
2. Add `healingeyesholistic.com`
3. Vercel provides DNS records
4. Update DNS at GoDaddy (A record + CNAME)
5. Wait 5min - 1hr for propagation
6. SSL auto-provisions

## Maintenance Notes

- **Updating prices:** Edit the relevant HTML file, push to git
- **Updating images:** Replace file in `assets/`, push to git (filename must match)
- **Adding pages:** Create new `.html` file, optionally add rewrite to `vercel.json`

## Page Sizes

- `index.html` — ~33 KB
- `foundation-course.html` — ~30 KB
- `academy.html` — ~37 KB
- Total assets — ~1.6 MB (cached on first visit, then served from CDN)

## Built With

This site was designed and built as part of the Healing Eyes infrastructure project (Bloom Harvest LLC, April-May 2026). Pages are intentionally minimal-dependency for maximum performance and longevity.
