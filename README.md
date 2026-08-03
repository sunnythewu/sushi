# Japanese Meal Picker 🍥

Can't decide what to eat? This single-page app helps you pick a Japanese meal — filter by mood, browse by category, search by keyword, or let the dice decide with a single click.

**Live site:** <https://sunnythewu.github.io/sushi/>

## Features

- **22 Japanese meals** — from sushi and ramen to kaiseki and takoyaki, each with a description, rough price range, best time of day, and matching moods
- **Mood filters** — Quick & cheap, Comfort food, Healthy, Share with friends, Celebrate
- **Search & categories** — filter by keyword (e.g. "noodle", "hotpot", "beef") or category (Noodles, Fried, Hotpot, Set Meals, Fine Dining…)
- **🎲 Surprise me** — picks a random meal from the currently visible set and scrolls to it
- **Fully offline** — a single HTML file plus local images; no internet or dependencies required

## Quick start

Open [index.html](index.html) in any modern browser, or visit the live site above.

## How to use it

1. Tap one or more **moods** to narrow the grid to meals that fit the vibe.
2. Use the **search box** or **category chips** to refine further.
3. Hit **🎲 Surprise me** to let fate choose; the card is highlighted and the page scrolls to it.
4. **Reset** clears all filters.

> Prices are rough per-person guides — a conveyor-belt sushi lunch and an omakase counter cost very different amounts.

## Project structure

```
.
├── index.html   # The whole app — markup, styles, and logic in one file
├── img/         # Dish illustrations (local, so the page works offline)
└── README.md
```

## Customizing

All meals live in the `MEALS` array inside the `<script>` block of [index.html](index.html).

Each meal has:

```js
{
  name: "Ramen",
  jp: "ラーメン",          // Japanese name
  emoji: "🍜",
  cat: "Noodles",          // category (shown as a filter chip)
  price: "$10–20",         // rough per-person guide
  time: "Lunch · Dinner",  // best time of day
  moods: ["comfort", "quick"], // which mood filters match
  desc: "Wheat noodles in rich broth…"
}
```

To add a dish:

1. Add an entry to `MEALS`.
2. Add a line to the `IMG` map: `"Ramen": "ramen"`.
3. Drop the illustration at `img/ramen.png` (800×600 works best; transparency is supported).

To add a mood, add it to `MOODS` and tag relevant meals with its id.

## Deployment

The site is published with **GitHub Pages**, configured to deploy from the `main` branch at the repo root. Any `git push` to `main` automatically rebuilds the live site — there's nothing else to run.

## Credits & notes

- Food illustrations are free-to-use artwork from [Illustcenter](https://illustcenter.com) — used per their terms.
- Prices, "best time" labels, and mood tags are editorial guidance, not absolute rules.
- Built as a single self-contained page so it can also be shared as one file.
