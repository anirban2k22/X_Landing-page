# Xcelerator — landing page

One file: `index.html`. Open it in any browser, or drop it on any host
(Netlify, Vercel, GitHub Pages, S3). No build step, no dependencies to install.

## Publishing on GitHub Pages
Push this folder to a repo → **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.
`index.html` is served at the repo URL within a minute. `.nojekyll` stops Jekyll from touching the file.

## Two pages in one file
- **Home** — hero → "Let's be honest" → beliefs → journey → how we make learning exciting →
  more than a company → proof → stories → community → closing banner
- **Who we are?** — opens from the nav link (the only nav item kept, as marked in red on the mock)

Both are `<main data-view="...">` blocks; the nav swaps them. To split them into two real
URLs later, cut each `<main>` into its own file and change the nav links back to `href`.

## Editing content
Everything repeatable lives in the `SITE` object in the second `<script>` — names, roles,
quotes, stat numbers, video questions, community cards, team, timeline, sayings, and all
social links. Headline copy sits directly in the HTML, marked with comment banners.

- **Icons** are Lucide names (https://lucide.dev/icons). Change `icon:"trophy"` → any name.
- **Photos** every `photo: ""` renders a drawn placeholder. Paste a real image URL to replace it:
  `{ name:"Kaushik", line:"…", photo:"/img/kaushik.jpg" }`
- **Colours / spacing** are CSS variables in `:root` at the top of the `<style>` block.
- **Logo** is embedded as base64 (`LOGO_DARK`, `LOGO_LIGHT`) so the file stays portable.

## What's generated vs. supplied
Your logo files are used as-is. Every person, thumbnail, collage photo, the hero scene, the
dusk banner and the "together" art are SVG illustrations drawn in the file — placeholders in
your palette, so nothing is stock and nothing 404s. Swap them for real photography when you have it.

## Built in
Scroll reveals, marker strokes that draw themselves, counters that count up, hover states,
keyboard focus, `prefers-reduced-motion` respected, responsive down to 360px.

## Files
```
index.html        the whole site (styles, scripts, artwork, logo all inlined)
README.md         this file
assets/           original logo PNGs, kept for reference — the page does not load them
.nojekyll         tells GitHub Pages to serve the file as-is
```
