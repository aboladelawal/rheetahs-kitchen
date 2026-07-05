# Rheetah's Kitchen

Editorial brand site for Rita Mensah (Chef Rheetah), food vendor and founder of Rheetah's Kitchen, Lagos. Built by [Alpha Global Tech and Consulting](https://agtconsults.com/).

Astro static site. Vanilla CSS with design tokens, no framework, no UI kit. Reference look: GAIL's Bakery — cream ground, one warm orange accent, Fraunces over Inter, sticky compact nav, magazine-style sections.

## Stack

- **Astro 5** (static output). Images optimised at build via `astro:assets`.
- **Fonts:** Fraunces (display serif) + Inter (body), self-hosted via `@fontsource-variable`.
- **CSS:** one design-token system in `src/styles/global.css`. Minified with lightningcss.

## Develop

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # → dist/
npm run preview  # serve the built site
```

## Structure

```
public/media/            # video + posters, served as-is (hero, box clips)
src/
  assets/img/            # stills + logos, optimised by Astro
  components/            # Nav, Footer, ProductCard, Marquee
  layouts/Base.astro     # cream homepage shell (Nav + Footer + SEO head)
  pages/
    index.astro          # single editorial scroll (all sections)
    gwr.astro            # standalone dark/gold Guinness World Record page
  styles/global.css      # design tokens + shared helpers
```

## Pages & sections

- **`/`** — Hero (video) · Story ("In her honour") · Signatures · Catering grid · Curated boxes · In the kitchen · Fruity Zobo · Team · GWR teaser · Contact. Nav links are in-page anchors.
- **`/gwr`** — dedicated near-black + gold prestige page for the Guinness World Record attempt (own colour scheme, cream logo).

## Brand tokens (`global.css`)

```
--brown #41210A   --brown-deep #2A1607   --brown-soft #6B4A33
--orange #F27326  (single accent)
--cream #F8F1E4   --cream-card #FFFDF8
GWR scope: --gwr-ink #0E0B08  --gwr-panel #14100B  --gwr-gold #C7A15A  --gwr-cream #F2E9D6
```

Semantic aliases (`--ink`, `--paper`, `--terracotta`, …) map onto the brand tokens so the forked GAIL's components reskin cleanly.

## Editing

- **Copy** lives in `src/pages/index.astro` and `src/pages/gwr.astro`.
- **Swap a photo:** replace the file in `src/assets/img/` (Astro re-optimises on build) or `public/media/` for video.
- **Contact / WhatsApp:** phone `+234 912 950 8724`, WhatsApp `wa.me/2349129508724`, email `rheetahskitchen@gmail.com`, IG `@rheetahs_kitchen`.

## Open items (waiting on the client)

- **Fire Feast X signature card:** hero photo pending — card ships with a reserved placeholder frame.
- **Jollof card image:** currently the best jollof shot from the existing content; swap when a hero shot arrives.
- **Restaurant address & hours:** pending — Contact runs without a location block until provided (no address invented).
- **More catering / boxes / kitchen shots:** slots are easy to extend as photos come in.

## Facts that must stay correct

Food vendor, chef, and founder (not a personal chef). Started cooking 2019, launched Rheetah's Kitchen 2021. Always "in her honour," never "in memory." Self-taught — no "trained under" claim, no Hilda Baci. GTCO **Food and Drink Festival** 2026 (9th edition), one of 204 vendors, sold out three days running; payments partner **Squad by GTCO**. GWR longest cooking marathon (individual) current holder: Evette Quoibia, 140 hr 11 min 11 sec, Melbourne, February 2024.

## Deploy

Vercel (`vercel.json` sets the Astro preset) or Netlify (`netlify.toml`). Build command `npm run build`, output `dist/`.
