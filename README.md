# BAND-MAID Tour History Map

An unofficial interactive world map of every BAND-MAID live show, plotted by venue. Built as a companion to the [BAND-MAID Unofficial](https://drivetimebm.github.io/BAND-MAID_gpt/) fan app.

**Live:** [drivetimebm.github.io/BAND-MAID_map](https://drivetimebm.github.io/BAND-MAID_map/)

---

## Features

- **World map** with a pin for every show, color-coded by region
- **Venue grouping** — multiple shows at the same venue share one marker; click to see all dates
- **Setlist expansion** — click any show row in the popup to reveal the full setlist, with the opener and closer highlighted
- **Filters** — narrow by Tour, Country, or Year; stats update live
- **Marker clustering** — nearby pins cluster at low zoom and expand as you zoom in

## Region Colors

| Color | Region |
|-------|--------|
| 🟡 Gold | Japan |
| 🔵 Teal | Asia / Pacific |
| 🟢 Green | North America |
| 🔴 Red | Europe |
| 🟣 Purple | Other |

## Data Source

Show data is pulled at runtime from the [okyuji.json](https://drivetimebm.github.io/BAND-MAID_gpt/okyuji/okyuji.json) feed in the `BAND-MAID_gpt` repo. Each entry includes date, venue, city, country, tour name, coordinates, setlist, and a setlist.fm link.

Coordinates are venue-accurate for most shows. A small number of older or smaller shows use a city-center point.

## Tech Stack

- [Leaflet.js](https://leafletjs.com/) — map rendering
- [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) — cluster plugin
- [CartoDB Dark Matter](https://carto.com/basemaps/) — tile layer
- Vanilla HTML/CSS/JS — no build step, no dependencies to install

## Deployment

The map is a single `index.html` file hosted on GitHub Pages. To deploy updates, run the included PowerShell script:

```powershell
.\New-BandMaidMapRepo.ps1 -Token "ghp_xxxxxxxxxxxx" -IndexHtmlPath ".\index.html"
```

The script creates the repo (if it doesn't exist), commits `index.html`, and enables GitHub Pages via the GitHub REST API — no local git installation required.

A PAT with `repo` scope is required.

## Related Projects

| Repo | Description |
|------|-------------|
| [BAND-MAID_gpt](https://github.com/drivetimebm/BAND-MAID_gpt) | Main fan app — JSON-driven, multi-view |
| [BAND-MAID_reports](https://github.com/drivetimebm/BAND-MAID_reports) | Report viewer with charts and PDF preview |
| [BAND-MAID_sorter](https://github.com/drivetimebm/BAND-MAID_sorter) | Pairwise song preference sorter |

---

*Unofficial fan project. Not affiliated with BAND-MAID or their management.*
