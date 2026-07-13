# RouteAtlas

Single-file HTML app for visualising multiple GPX routes together on an OS map, grouped and colour-coded.

**Live app:** https://njclarke1.github.io/routeatlas/

## Setup

1. Open the live URL in Chrome.
2. On first run, Settings opens automatically — paste in an OS Maps API key.
   - Free key from [osdatahub.os.uk](https://osdatahub.os.uk) — create a project, add the **OS Maps API** (not Vector Tile API).
   - Without a key the app falls back to OpenStreetMap tiles.
3. Chrome menu → **Add to Home screen** for an app-like icon.

## Use

- **Import GPX** — pick or drag-drop multiple `.gpx` files at once, assign the whole batch to a new or existing group.
- Click a group's swatch to change its colour; click a route's dot for a per-route colour override (right-click the dot to clear the override and revert to group colour).
- Eye icons toggle visibility per group or per route. Compass icon zooms to a group.
- Data is stored in the browser's IndexedDB, scoped to this origin (`njclarke1.github.io`) — it does not sync across devices or origins.

## Updating

Repo → the file → pencil icon for small edits, or **Add file → Upload files** to overwrite `index.html` wholesale. GitHub Pages redeploys automatically within about a minute.

## Status

P1 MVP. Known gaps, planned for later phases:
- OS Leisure (1:25k Explorer) layer as an alternative to Outdoor
- JSON export/import of the full route library
- Distance-based colour ramps
- Per-route "completed" flag
- PWA manifest + service worker for offline use

## Stack

Single HTML file, Leaflet (CDN), IndexedDB, no build step, no server-side component. OS Maps API key is entered at runtime and stored only in the browser — never committed to this repo.
