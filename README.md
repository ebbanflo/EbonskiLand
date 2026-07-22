# Ebonski Land

The master link hub for Ebb's projects — a single page that routes out to the
GitHub Pages apps and repos worth showcasing.

Live page: `index.html` (served via GitHub Pages).

## What's here
- CSS-3D wayfarer glasses in the center with a personality: they look
  around on their own, sometimes follow your cursor, sometimes stare
  right at you (leaning in), blink, and cock their head — a tiny state
  machine drives the mood swings.
- Gloopy, mouse-reactive **Ebonski Land** title (Cooper Black).
- The whole page tilts in 3D toward your cursor, with the title and
  sections floating at different depths for real perspective parallax.
- Borderless floating type sections that drift, parallax, and link out
  to each project. No libraries, no SVG filters — everything animates
  with GPU transforms, so it loads instantly and stays smooth.

## Adding / editing projects
Everything is data-driven. Open `index.html`, find the `PROJECTS` config near
the bottom of the file, and edit the array. No other changes needed.

```js
const PROJECTS = [
  {
    title: "Music Ideas",
    emoji: "🎵",
    pos: { top: 22, left: 6 },   // rough anchor on wide screens (% of viewport)
    links: [
      { name: "Musiicode", url: "https://ebbanflo.github.io/Musiicode/" },
      // add more { name, url } here...
    ],
  },
  // ...add a whole new section object to create a new floating card
];
```

- `pos` accepts any of `top` / `bottom` / `left` / `right` as percentages.
  Use `left: 50` to center a card horizontally.
- On narrow screens the cards ignore `pos` and stack vertically automatically.

## Notes on links
Links point at the expected GitHub Pages URLs
(`https://ebbanflo.github.io/<repo>/`). If a project isn't published to Pages
yet, enable Pages on that repo (or swap the URL for the repo/other host).
