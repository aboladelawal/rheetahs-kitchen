# Rheetah's Kitchen — Personal Brand Site

Single-page editorial site for Rita Mensah (Chef Rheetah), founder of Rheetah's Kitchen, Lagos.

## What's inside

```
index.html               — the whole site (one file, inline CSS + JS)
assets/
  video/
    hero.mp4             — hero loop, high bitrate (~7.7MB, desktop)
    hero-mobile.mp4      — smaller version for mobile (~3.7MB)
    hero-poster.jpg      — fallback poster image
  images/
    portrait.jpg         — Chef Rheetah formal chef-coat portrait
    favicon.png          — browser tab icon (logo crop)
    og-image.jpg         — 1200×630 link preview card
    logo-crimson-sm.png  — transparent logo, crimson (for cream backgrounds)
    logo-cream-sm.png    — transparent logo, cream (for crimson/dark backgrounds)
    work-*.jpg           — portfolio photos for the work sections
```

Total site weight: ~16MB. Loads fast on Lagos mobile networks because the heaviest assets (video, hi-res photos) are lazy-loaded.

## Sections, in order

1. **Hero** — layered composition: logo, eyebrow pill, big serif headline, byline, services, video card with gold corner ticks, bottom credentials strip
2. **Story** — editorial intro + the clickable CEO card → opens Rita's bio modal
3. **Catering & Events** — first work category, big hero image + two supporting tiles
4. **Signature Dishes** — three numbered (i/ii/iii) editorial spreads: pineapple boat pasta, seafood okra, akara & pap
5. **Curated Boxes & Gifting** — date box, picnic basket, branded packs
6. **GTCO Feature** — gold banner, big headline, two GTCO photos, pull quote, 4 stats strip
7. **Cook-a-thon** — GWR attempt, 2026/27 (TBC), become-a-partner CTAs
8. **Behind the Service** — cinematic split with pull quote, then a 3-tile BTS grid
9. **Contact** — WhatsApp, call, IG, email — all clickable
10. **Footer**

## How to deploy

**Netlify (fastest)**
1. Go to netlify.com → drag the entire `rheetahs-kitchen-site` folder onto the dashboard
2. You get a URL like `chef-rheetah.netlify.app` instantly
3. To use a custom domain (e.g. `rheetahskitchen.com`), buy the domain → point DNS to Netlify

**Vercel**
1. vercel.com → new project → upload folder → deploy

**GitHub Pages**
1. Create a repo, push the folder contents
2. Settings → Pages → Source: main branch → save

No build step. No framework. Static HTML — drops onto any web host.

## Things to confirm with Rita

I wrote the copy in her voice based on the assets and brand. These spots need her sign-off:

1. **Bio paragraphs in the modal**. I assumed:
   - Founded Rheetah's Kitchen in 2020
   - Featured Vendor at GTCO Food & Drink Fair, 2025
   - Partnered with Squad by Sterling Bank for payments
   
   If any of these years or details are wrong, edit directly in `index.html` (search for `class="modal-bio"`).

2. **Story intro paragraph** (Section 01). Confirm the founding-story phrasing rings true.

3. **Cook-a-thon details** (Section 05). Placeholders:
   - Target: "Beat 140+ hrs"
   - Window: "2026 / 27" with "Date to be confirmed"
   - For: "Community plates" / "Every hour cooked, fed forward"
   
   Once the plan is locked, update these values.

4. **GTCO feature copy**. The quote about her stand having "the operational discipline of a restaurant ten times her size" is mine — confirm she likes it or replace.

5. **Email address**: I used `hello@rheetahskitchen.com`. If she doesn't own that domain yet, buy it + set up Google Workspace, OR replace with whatever email she actually uses for brands/press. Find/replace in `index.html`.

6. **Copyright year**: footer currently says "© 2026". Update annually.

## Editing tips

- All copy lives in `index.html`. No separate files. Open in any text editor.
- Brand colours are CSS variables at the top of the `<style>` block. Search for `--crimson:` to find them.
- To swap a photo: replace the file in `assets/images/` with the same filename. No code changes needed.
- To swap the hero video: replace `assets/video/hero.mp4` (desktop) and/or `hero-mobile.mp4`. Keep vertical (720×1280) for best mobile performance.
- Section IDs for direct linking: `#story`, `#work`, `#feature`, `#cookathon`, `#contact`

## Browser support

Tested in modern Chrome, Safari, Firefox. Works on iOS Safari (autoplay video uses `muted playsinline`). Designed mobile-first at 390px viewport, scales up to 1440px+ desktop.

---

Questions: ask Bolade.
