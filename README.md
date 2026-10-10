# Nails by Aubs

One-page site for nailsbyaubs.com. Astro, deployed to GitHub Pages (same setup as islandtwigstudios.com).

## Adding photos

Drop files in `src/assets/` and push. Astro resizes and compresses them at build time, so phone photos are fine as they are.

- `src/assets/gallery/` : gallery photos (jpg, png, or webp). Up to 16 is ideal, 8 per row. They're split across the two rows in filename order, so `01.jpg`, `02.jpg`, ... controls the order. With none, the page shows placeholder tiles.
- `src/assets/aubrey.jpg` : headshot for the arch frame (any of jpg, png, webp).
- `src/assets/logo.png` (or `.svg`) : shown in the nav in place of the blush dot.

## Contact form

The form posts to Formspree, which emails Aubrey each submission.

1. Make a free account at formspree.io and create a form that sends to Aubrey's email.
2. Copy its endpoint (looks like `https://formspree.io/f/abcdwxyz`).
3. Paste it into `FORM_ENDPOINT` at the top of `src/pages/index.astro`.

Until that's done, the form shows an error instead of sending.

## Run locally

```
npm install
npm run dev
```

## Deploy

Pushing to `main` builds and publishes via `.github/workflows/deploy.yml`. In the repo, go to Settings, then Pages, and set Source to "GitHub Actions". The custom domain comes from `public/CNAME`.
