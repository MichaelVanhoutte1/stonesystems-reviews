# stonesystemsreviews.com

Static one-page review wall for Stone Systems.

## What's on the page

1. **Hero** — headline, stats (1,150+ clients, 4.1★ Trustpilot, 4.8★ Google), CTA
2. **Video Testimonials** — 33 videos pulled from Supabase storage (lazy loaded)
3. **Written Quotes** — 20 client quotes from the main website
4. **Google Reviews** — placeholder (4.8★ / 56 reviews badge) — needs Place ID to go live
5. **Trustpilot Reviews** — 79 positive reviews scraped live (4.1★ / 103 reviews)
6. **Footer**

## Deploy to Vercel (recommended)

```bash
# From this directory
npx vercel --prod
# Set custom domain: stonesystemsreviews.com
```

Or drag-and-drop this folder to Vercel dashboard → Import from directory.

## Deploy to Netlify

```bash
# Drag this folder to netlify.com/drop
```

## Adding Google Reviews

1. Find Stonesystems' Google Business Place ID (go to Google Maps → search for "Stone Systems" → share → copy CID from URL)
2. Replace the placeholder section in `index.html` with the live reviews fetched via:
   `https://maps.googleapis.com/maps/api/place/details/json?place_id=PLACE_ID&fields=reviews&key=API_KEY`
   Note: Google Places API only returns 5 most recent reviews max. For full reviews, use a third-party scraper or embed a Google reviews widget.

## Refreshing Trustpilot Reviews

Run this to re-scrape and regenerate:
```bash
node /tmp/scrape_tp_full.js > /tmp/tp_new.json
# Then rebuild index.html using the Python script
```

## Domain
Point `stonesystemsreviews.com` DNS to Vercel/Netlify after deploy.
