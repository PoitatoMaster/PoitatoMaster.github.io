# Portfolio site

Plain static HTML/CSS/JS — no build step, no framework. Ready to deploy on GitHub Pages.

## Structure

```
index.html      main page
styles.css      all styling (design tokens at the top)
script.js       mobile nav + scroll-spy, ~40 lines total
assets/         CV PDF and any images you add
```

## Deploy to GitHub Pages

1. Create a new repo on GitHub (e.g. `yourusername.github.io` for a root domain, or any name like `portfolio`).
2. Push these files to the repo root:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Set branch to `main` and folder to `/ (root)`, then Save.
6. Your site goes live at:
   - `https://<your-username>.github.io/` — if the repo is named `<your-username>.github.io`
   - `https://<your-username>.github.io/<repo-name>/` — for any other repo name

Give it a minute or two after the first push before it's reachable.

## What's still placeholder

- **Field trial photo** in the Experience section (mission log) — swap in a real image from a Maviyom deployment.
- **Project figures** (Hypersonic Inlet Buzz, FSI Decompression, Formula Student) are schematic line-art stand-ins — swap for actual CFD contour plots, schlieren stills, or the real aero package photos when you have them.
- All copy is pulled directly from the CV — nothing invented, so it should hold up as-is, but tighten anything that reads off.

## Swapping a placeholder image

Each placeholder is inline SVG inside `index.html`. Easiest path: drop a real image into `assets/`, then replace the relevant `<svg>...</svg>` block with:

```html
<img src="assets/your-image.jpg" alt="Description of the image">
```

## Customizing

- Colors, fonts, spacing: all defined as CSS custom properties at the top of `styles.css` under `:root`.
- Sections can be reordered, removed, or duplicated directly in `index.html` — each is a self-contained `<section>`.
