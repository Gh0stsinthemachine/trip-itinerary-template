# Trip Itinerary — static site template

A two-page, no-build static site for a trip itinerary + a local "eat & play" guide.
Pure HTML/CSS with a sprinkle of vanilla JS (scroll reveals). Designed to drop onto
Vercel (or any static host) with zero dependencies.

This is a **sanitized example** — the booking confirmation numbers, addresses, and
photos are placeholders. Swap in your own.

## Pages

- `index.html` → the itinerary (journey ribbon, photo "stop" cards, the headline
  event ticket, logistics, a pre-trip checklist, and a confirmation-number ledger),
  served at `/`
- `guide.html` → a per-stop guide of places to eat and things to do, with cinematic
  section banners, served at `/guide`
- `vercel.json` → `cleanUrls` on, so `/guide` resolves without the `.html`

## Design notes

- **Fonts:** Unbounded (display) + Outfit (text), via Google Fonts.
- **Palette:** navy / terracotta / gold / paper — defined as CSS variables at the top
  of each file's `<style>` block.
- **Photos** live in `photos/` as WebP. Three patterns are used:
  - *Ghosted washes* — a photo behind a navy panel at ~10–12% opacity with
    `mix-blend-mode: soft-light`, toned to the palette (hero, footer, ticket).
  - *Photo cards* — a real image baked into an itinerary card, fading into the card
    via a gradient seam (`.pcard`).
  - *Section banners* — a wide locale photo with the title overlaid (`.vbanner`).
- Fully responsive; everything collapses to a single column on phones.

## Make it yours

1. Replace the copy in `index.html` / `guide.html`.
2. Drop your own images into `photos/` (keep the filenames, or update the `src`/`url()`
   references). WebP keeps them light — `cwebp -q 70 in.jpg -o out.webp`.
3. Update the colors via the CSS variables if you want a different mood.

## Deploy

```bash
vercel --prod        # from this folder, with the Vercel CLI authenticated
```

Or import the repo in the Vercel dashboard — it's a static site, no framework preset
needed.

## Photo credits / licensing

The placeholder and locale images in `photos/` are sourced from
[Wikimedia Commons](https://commons.wikimedia.org) (various Creative Commons licenses)
and public hotel marketing pages, included here purely as **example placeholders**.
Replace them with your own imagery before using this for anything real, and honor the
original licenses if you keep any.
