# VowSuite Wedding Planning Studio

Advanced static wedding planning studio for planners, couples, vendors, and wedding-day operations.

Live app: https://gab8511.github.io/wedding-planning-studio/

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-2ea44f)](https://gab8511.github.io/wedding-planning-studio/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Features

| Area | Included |
| --- | --- |
| Planning command center | Executive dashboard, readiness scoring, progress metrics, risk indicators |
| Guests | RSVP tracking, meals, contact fields, relationships, CSV import/export |
| Budget | Payments, cash flow, tax/service/tip modeling, category tracking |
| Vendors | Pipeline, contract status, insurance status, vendor timelines |
| Timeline | Task board, dependencies, phase templates, run-of-show planning |
| Wedding day | Mobile wedding-day mode, production notes, packing and floor-zone planning |
| Seating | Seating planner with rule warnings and drag/drop seat moves |
| Reports | Client packets, vendor packets, HTML packet export |
| Studio ops | Leads, proposals, invoices, message templates, saved couples |
| Portals | Client portal preview with PIN and vendor portal preview |

## Preview

The app is published with GitHub Pages:

https://gab8511.github.io/wedding-planning-studio/

Screenshots will live in [`docs/screenshots`](docs/screenshots) as the visual documentation set grows.

## Run Locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 4173
```

Then open:

```text
http://127.0.0.1:4173/
```

## Deploy

This is a static app published with GitHub Pages from the `main` branch and repository root.

Live deployment:

```text
https://gab8511.github.io/wedding-planning-studio/
```

## Data Storage

The app currently stores plans in browser local storage. Use **Export plan** and **Import plan** to move plans between devices or browsers.

Read the privacy note before entering real client, guest, vendor, financial, or contract data: [PRIVACY.md](PRIVACY.md).

## Project Docs

- [Changelog](CHANGELOG.md)
- [Roadmap](ROADMAP.md)
- [Privacy](PRIVACY.md)
- [License](LICENSE)
