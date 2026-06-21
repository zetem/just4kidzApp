# just4kidz

A map-first activity discovery dashboard for parents, built with React 18. Find kids' activities near you, see live availability, and explore by category — all on an interactive neighborhood map.

![just4kidz dashboard](https://github.com/zetem/just4kidzApp/raw/main/screenshots/dashboard.png)

## Features

- **Interactive map** — stylized neighborhood map with category pins; click any pin to see details
- **Live availability** — open, filling fast, and full status on every activity
- **Filter chips** — filter by Open now, Sports, Arts, Outdoor, Music, or Water
- **Collapsible sidebar** — nav, logo, and a community friends panel
- **Detail popover** — price, location, age range, schedule, and save button
- **No build step** — runs directly in the browser via ES module imports

## Tech stack

| Layer | Choice |
|---|---|
| UI library | React 18 (via `esm.sh` ES modules) |
| Styling | CSS custom properties (design tokens) |
| Icons | Inline SVG (Lucide-style) |
| Fonts | Plus Jakarta Sans + DM Mono (Google Fonts) |
| Data | Static mock data (in-file) |

## Getting started

No install required. Just open `index.html` in Chrome or Edge.

```bash
# Clone
git clone https://github.com/zetem/just4kidzApp.git
cd just4kidzApp

# Open directly — no server needed
start index.html        # Windows
open index.html         # macOS
xdg-open index.html     # Linux
```

> Requires an internet connection on first load to fetch React and fonts from CDN.

## Project structure

```
just4kidz/
├── index.html      # Complete app — React components, styles, and data
└── README.md
```

## Component overview

```
Dashboard               ← root, owns all state
├── SideNav             ← collapsible sidebar, nav items, friends panel
├── AppHeader           ← search bar, CTA, user avatar
├── ResultsPanel
│   └── ActivityCard    ← category tag, availability pill, metadata
└── MapPane
    ├── MapView         ← abstract terrain + roads + city blocks
    │   └── MapPin      ← per-activity pin, expands on selection
    ├── FilterChips     ← open/sports/arts/outdoor/music/water
    └── DetailPopover   ← selected activity detail + save toggle
```

## Design tokens

All visual decisions — color, spacing, radii, shadows, motion — are defined as CSS custom properties at `:root`. Key token groups:

- `--color-primary` / `--color-primary-tint` — coral brand color
- `--cat-sports` / `--cat-arts` / … — per-category accent colors
- `--avail-open-*` / `--avail-filling-*` / `--avail-full-*` — availability status
- `--shadow-xs` → `--shadow-xl` — warm brown-tinted shadow scale
- `--radius-card` / `--radius-pill` — corner radius scale
- `--dur-base` / `--ease-spring` — motion tokens

## License

MIT
