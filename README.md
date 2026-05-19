# Atlas Flowers — Toshkent

Bilingual (UZ / RU) landing page for **Atlas Flowers**, a flower atelier in Tashkent. Built as a static site with an authentic khan-atlas (ikat) silk pattern running through the design.

🌐 [@atlas_flowers.uz on Instagram](https://instagram.com/atlas_flowers.uz)

## Features

- **Bilingual** — Uzbek (Latin script) as default, Russian on toggle. Language saved in localStorage.
- **Editable prices** — click any price tag in the catalog to type a number; saved to localStorage per bouquet.
- **Authentic atlas pattern** — generated via SVG `feTurbulence` filter for the characteristic "flame-licked" ikat edges. Used as selvedge stripe, silk-break dividers, and as pattern fill inside the giant ATLAS wordmark.
- **Tweaks panel** — palette switcher (Crema · Sahar · Tunda · Gulshan) and ornament density (minimal / balanced / rich).
- **Image slots** — drag-and-drop bouquet photos persist in `.image-slots.state.json`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main site (entry point for GitHub Pages) |
| `Atlas Flowers.html` | Same file with the original name — keep one, delete one |
| `atlas-pattern.svg` | The ikat textile pattern (used as background image) |
| `image-slot.js` | Web component for drag-and-drop photo slots |
| `tweaks-panel.jsx` | React tweaks panel (palette + ornament controls) |
| `.image-slots.state.json` | Persisted bouquet photos (base64). ~27MB — required for the dropped images to display |

## Deploy to GitHub Pages

1. Create a new repo on GitHub.
2. Push these files to the `main` branch.
3. Settings → Pages → Source: `Deploy from a branch` → branch `main` → folder `/ (root)`.
4. Site goes live at `https://<your-handle>.github.io/<repo-name>/`.

> The `.image-slots.state.json` file is fetched at runtime to display photos. Keep it next to `index.html`.

## Local preview

Any static server works:

```bash
python3 -m http.server 8000
# or
npx serve
```

Then open `http://localhost:8000/`.

## Stack

Vanilla HTML + CSS + a sprinkle of React (for the Tweaks panel). No build step required.
