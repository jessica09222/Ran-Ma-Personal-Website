[README.md](https://github.com/user-attachments/files/31686270/README.md)

# Ran Ma — Personal Website

Single self-contained `index.html` (no build step, no external JS libraries).
Just open the file, or drop the folder on any static host (GitHub Pages, Netlify, Cloudflare Pages).

```
index.html            the whole site (HTML + CSS + JS inline)
assets/portrait.jpg    hero portrait
assets/Ran-Ma-Resume.pdf   linked from the Contact section
```

## What was added in this pass

Light theme only — no dark mode. Bilingual (English / 简体中文) with a toggle in the nav.

- **EN / 中文 language toggle** (remembers choice; first visit follows the browser language).
  All translatable strings live in the `window.I18N` object at the bottom of `index.html` —
  edit Chinese wording there, keys map to `data-i="..."` attributes in the markup.
- Preloader, split-letter hero name, typewriter role line
- Auto-scrolling "impact numbers" marquee (pauses on hover)
- Count-up animation on the About stats
- Placeholder mini data-viz inside each Selected Work card (SVG — replace with real screenshots later)
- Small "career geography" map in Journey; click a pin to filter roles by region
- Skills panel now shows a proficiency meter per tool (self-assessed — edit the numbers)
- Copy-email button with toast, back-to-top button, right-edge section dots
- Magnetic buttons + trailing cursor ring on desktop
- Full `prefers-reduced-motion` and print stylesheet support

## Images

- **`assets/journey-map.jpg`** → the illustrated "My Journey" map (included, 1200px).
  Four invisible hotspots sit over the drawn pins: Zhangzhou (→ Education), Xiamen,
  Oxnard, Los Angeles (→ filter the timeline). If a hotspot is slightly off after you
  swap the image, tweak the `left` / `top` percentages on the `.jmap-pin` buttons in
  `index.html`.
- **`assets/edu-usc.jpg`** / **`assets/edu-jgu.jpg`** → campus photos in the Education
  cards (included). Swap the files (keep the names) to change them; if a file is missing
  the card falls back to a flat illustration automatically.
- `assets/portrait.jpg` → optionally a sharper / higher-res portrait
- add `assets/og-image.png` (1200×630) and point the `og:image` meta tag at it

## Text placeholders to confirm

- `class="viz"` blocks in Selected Work → illustrative charts, swap for real screenshots
- `data-level="…"` on `.skill-chip` → your real proficiency numbers (0–100)
- `window.I18N` (bottom of file) → review the Chinese; company names like "先锋期货" are
  best-guess translations. Cayi is tagged as Oxnard, CAFF as Los Angeles — adjust if wrong.
