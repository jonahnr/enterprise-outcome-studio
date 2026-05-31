# Parallax Data Lab Enterprise Outcome Studio

A customer-facing static web app for demonstrating enterprise transformation outcomes in a tangible way. The app helps Parallax Data Lab show how reporting modernization, semantic model trust, BI automation, and governance packaging translate into estimated customer value.

## What It Shows

- Enterprise benchmark proof points:
  - 75% reduction in eligible manual reporting effort
  - 25x query optimization and dashboard performance lift
  - 10x analytics delivery scale through BI engineering automation
  - RLS as an added governance package
- Customer-input outcome calculator using report volume, report-cycle effort, query usage, wait time, hourly cost, and automation eligibility
- Guided definitions for customer inputs so buyers understand what they are choosing
- Quick estimate mode and detailed report-inventory mode for mixed weekly/monthly reporting portfolios
- 0-100 readiness score based on weighted criteria with scoring guidance bands
- Readiness score blended from 80% self-assessment plus 20% operational pressure from manual reporting, query wait, model size, and logic issues
- Mutable semantic model trust layer with Power BI model-size, bad-logic, certification, duplicate-measure, and access signals
- Plain-language automation recipes with customer pain, mechanism, best fit, and proof artifacts
- Exportable outcome brief from the first-page results
- Editable detailed report inventory with add/delete rows
- Clickable governance package columns for comparison
- Governance packaging for Base, Scale, Audit, and RLS Add-on
- Capability catalog with unique visual cards, examples, and proof artifacts

## Run Locally

This is a static site. From the repo root:

```powershell
python -m http.server 4173
```

Then open:

```text
http://localhost:4173/index.html
```

You can also open `index.html` directly in a browser, but using a local server is closer to how it runs in GitHub Pages.

## Deploy With GitHub Actions

This repo includes a GitHub Actions workflow at:

```text
.github/workflows/deploy-pages.yml
```

The workflow publishes the static site to GitHub Pages whenever changes are pushed to `main`.

To enable it:

1. Push this repo to GitHub.
2. In GitHub, go to **Settings > Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Push to `main`.
5. Open the Pages URL shown after the workflow finishes.

## Repo Structure

```text
.
|-- .github/
|   `-- workflows/
|       `-- deploy-pages.yml
|-- .nojekyll
|-- README.md
`-- index.html
```

## Future Real-Data Integration

The current app is static and uses customer-entered inputs plus benchmark assumptions. A real-data version could replace those inputs with an API or data file that supplies:

- Report inventory and ownership
- Report cycle frequency and manual effort baseline
- Query runtime and dashboard usage logs
- Semantic model metadata
- Certified metrics and glossary records
- Governance, lineage, access, and RLS policy evidence

The recommended next step is to add a small data contract such as `data/outcomes.json`, then wire the calculator to load from that file before connecting to warehouse, BI, or governance APIs.
