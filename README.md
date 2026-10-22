# EVE Drawing & Quote Checker — No AI (V1.0)

Standalone browser-based tool for deterministic, rule-based comparison of digital drawing PDFs and DQM quote PDFs. This repository is separate from the EVE company website.

## Run locally
Open `index.html` in a modern browser, or serve this folder with any static HTTP server. PDF.js is loaded from cdnjs, so an internet connection is required to load the PDF text engine.

## Publish with GitHub Pages
1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, select **GitHub Actions** as the source.
3. The workflow in `.github/workflows/pages.yml` publishes the root folder when changes are pushed to `main`.
4. Once the workflow succeeds, the site is expected at https://evedesignandengineering-blip.github.io/eve-quote-checker-no-ai/

## Included
- Drawing and quote PDF upload and in-browser digital text extraction.
- Quote/drawing catalogue-code matching and discrepancy tables.
- CSV, text report and print/save-to-PDF exports.
- AUX_013 project-value rule: up to $50,000 = 1; $50,001–$200,000 = 3; above $200,000 = 12, subject to overhead applicability.
- AUX_005 rule using total internal cost less $174.13 per quoted AUX_005, divided into $10,000 bands and multiplied by four.
- CN54x → Cable_07 quantity × 2 check.
- DDrill installed/haul cross-check where a plausible polypipe match is present.
- Travel rule: standard OH/UG = 2 × depot road kilometres; switching crew = 6 × depot road kilometres, rounded to whole km.
- Diameter mapping guidance: 1/16/25 mm → 63 mm; 120/240 mm → 110 mm; 400 HV → 160 mm.

## Important limitations
This is a rule-based first release, not a full visual CAD/PDF understanding engine. It cannot reliably infer drawing geometry, count graphical symbols, interpret every legend, or OCR scanned PDFs. Text extraction heuristics can mistake a nearby number for a quantity. Uncertain items must be visually checked. The AUX_013 overhead applicability and travel item classification are not always inferable from text, so users must confirm them. The tool does not automatically fetch road distances or determine the nearest depot. The polypipe code mappings vary by quote/catalogue and require confirmation.

No AI APIs, API keys, Supabase, or EVE website endpoints are used. Files are processed locally in the browser and are not uploaded by this application. PDF.js is loaded from a public CDN.
