# VowSuite Wedding Planning Studio

Advanced static wedding planning studio for planners, couples, vendors, and wedding-day operations.

## Features

- Executive planning dashboard
- Guest CRM with RSVP, meals, contact fields, CSV import/export
- Budget studio with payments, cash flow, tax/service/tip modeling
- Vendor pipeline, contract status, insurance status, vendor timelines
- Timeline, task board, dependencies, phase templates
- Run-of-show and mobile wedding-day mode
- Seating planner with rule warnings and drag/drop seat moves
- Production planning for ceremony, music, photos, packing, floor zones, weather, and accessibility
- Reports, client packets, vendor packets, HTML packet export
- Documents and attachment metadata
- Studio management for leads, proposals, invoices, message templates, saved couples
- Client portal preview with PIN and vendor portal preview

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

This is a static app. You can publish it with GitHub Pages:

1. Push this folder to a GitHub repository.
2. In GitHub, open **Settings > Pages**.
3. Set source to the default branch and root folder.
4. Save and open the generated GitHub Pages URL.

## Data Storage

The app currently stores plans in browser local storage. Use **Export plan** and **Import plan** to move plans between devices or browsers.
