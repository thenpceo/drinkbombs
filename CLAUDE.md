# DrinkBombs — Claude Context

## What This Project Is
A marketing landing site for **Drink Bombs** — fizzy cocktail spheres you drop into sparkling water. The site is pre-launch, focused on email capture, brand hype, and driving variety pack sales.

**Founder:** Chloe Di Leo. Woman-owned, Houston-made. Origin story: Hurricane Harvey, a kid eating Pop Rocks, a call to a chemist.

---

## Tech Stack
- **Pure HTML/CSS/vanilla JS** — no frameworks, no build tools, no npm
- All styles are **inline in each HTML file** (inside `<style>` tags in `<head>`)
- All JS is **inline at the bottom** of each HTML file (before `</body>`)
- No external dependencies except Google Fonts

## File Structure
```
site/
  index.html          — main landing page (homepage)
  our-story.html      — founder story + clean ingredients
  product.html        — product detail page (WIP)
  images/
    logo.png
    margarita.png
    cosmopolitan.png
    moscow-mule.png
    old-fashioned.png
    espresso-martini.png
    margarita-lifestyle.jpg   — lifestyle shot: sphere dropping into margarita glass
    martini-line-art.png      — decorative background element
    ingredients-bg.jpg        — background for ingredients section
    hero-video.mp4            — hero background video
```

## Dev Server
```
python3 serve.py   (configured in .claude/launch.json)
```
Use `preview_start "DrinkBombs"` to launch. Port auto-assigns if 3000 is in use.

---

## Design System

### Colors (CSS variables)
```css
--ruby: #E8364F          /* primary red accent */
--margarita: #4ADE80     /* green — Margarita flavor */
--cosmo: #F472B6         /* pink — Cosmopolitan flavor */
--mule: #FB923C          /* orange — Moscow Mule flavor */
--old-fashioned: #FBBF24 /* yellow — Old Fashioned flavor */
--espresso-accent: #A17256 /* brown — Espresso Martini flavor */
--emerald: #34C470       /* green for ingredients/clean */
--ink: #1C1C1E           /* near-black for text + dark sections */
--ink-light: #6B7280     /* body text gray */
--surface-subtle: #F8F8F8 /* light gray backgrounds */
```

### Fonts
```css
--font-display: 'Unbounded'   /* headings — bold, geometric */
--font-body: 'DM Sans'        /* body copy */
```

### Key CSS Patterns
- Section padding: `var(--section-pad)` = `clamp(60px, 10vw, 120px)`
- Side padding: `var(--side-pad)` = `clamp(20px, 5vw, 80px)`
- Reveal animation: add `.reveal` class, JS IntersectionObserver adds `.visible`
- Color accent strips between sections: `<div class="color-strip color-strip-[green|pink|orange|yellow|gradient]"></div>`
- Buttons: `.btn-primary` (dark pill), `.btn-secondary` (outline pill)

---

## Homepage Sections (in order)
1. Announcement bar
2. Nav
3. Hero (video background, "Craft Cocktails in 3 Seconds")
4. Color marquee strip
5. Social proof bar (TikTok, BuzzFeed, Refinery29, Food & Wine, Bon Appétit)
6. **Lifestyle feature** — margarita-lifestyle.jpg split section, "Watch It Drop."
7. How It Works / Bloom Effect (3 steps: Drop, Fizz, Drink)
8. Product showcase (5 flavor cards)
9. Bloom Effect experience section (dark panel + feature list)
10. Testimonials (dark background)
11. CTA / Variety Pack ($59, save 20%)
12. FAQ accordion
13. Footer

## Our Story Page Sections
1. Page hero — "Born From a Pop Rock Moment"
2. Founder story (Chloe Di Leo, Hurricane Harvey origin)
3. Clean ingredients (Natural Flavors, Acid Balance, Effervescence, Monk Fruit)
4. CTA strip — sends back to shop
5. Footer

---

## Products & Pricing
| Flavor | Tag | Notes |
|---|---|---|
| Margarita | BEST SELLER | Lime · Citrus · Salt Rim |
| Moscow Mule | — | Ginger · Lime · Copper Kick |
| Cosmopolitan | — | Cranberry · Citrus · Pink |
| Old Fashioned | NEW | Orange · Bitters · Bourbon |
| Espresso Martini | PREMIUM | Coffee · Vanilla · Rich |

- Individual: 2-Pack $9.99 / 4-Pack $17.99
- Variety Pack: $59 (was $74.95, save 20%) — 5 flavors, 10 bombs

## Quiz
- "Party Drink Vibe Quiz" — 3 questions → flavor match → email gate → 15% off code `VIBES15`
- Triggered by "Find Your Flavor" button
- JS object: `quiz.open()`

---

## Brand Voice
- **Tone:** Fun, confident, punchy. Short sentences. Not cutesy.
- **Tagline:** Drop. Fizz. Drink.
- **Good copy examples:** "Zero Bartending. Maximum Theater." / "The Moment Everyone Pulls Out Their Phone" / "Watch It Drop."
- **Avoid:** corporate language, overly feminine/girly tone, long paragraphs
- **Key claim:** craft cocktail in 3 seconds, no bartending required, alcohol optional

## Key Decisions Already Made
- Founder Story + Clean Ingredients live on `our-story.html`, NOT the homepage (moved to shorten homepage scroll)
- Nav "OUR STORY" links to `our-story.html`
- Hero uses video background (`hero-video.mp4`) on desktop, stacks below text on mobile
- Lifestyle photo section sits between Social Proof Bar and How It Works
