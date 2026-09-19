# Bahir Dar urban growth — project brief

## The question
How much has the built-up area of Bahir Dar expanded since 2015?

## Why it matters
Bahir Dar has grown fast along the Lake Tana shoreline over the past decade, and the city's structure plan and land administration office need current, evidence-based figures on where and how much new built-up land has appeared. A clear before/after measurement would let planners and researchers see the scale of expansion at a glance, and give a first, lightweight companion to a fuller land-use change study already underway for the city.

## The data I need
- Built-up surface area, 2015 and 2025 — to measure the change directly
- Settlement extents, current — to cross-check the built-up layer against a second source
- Satellite imagery, 2015 and 2025 — to visually confirm the measured change on the ground

## Where each dataset comes from
- **Built-up surface (GHS-BUILT-S)** — European Commission Joint Research Centre (GHSL programme) — https://developers.google.com/earth-engine/datasets/catalog/JRC_GHSL_P2023A_GHS_BUILT_S — GeoTIFF grid, 100 m resolution, global coverage in 5-year steps from 1975–2030 (2015 and 2025 epochs both exist); accessed for free through Google Earth Engine, clipped to a Bahir Dar boundary — no multi-hundred-MB download needed
- **Settlement extents** — GRID3 (CIESIN, Columbia University) — https://data.grid3.org/datasets/5bf298c9a55141a082911b406068e276_0/explore — GeoPackage/shapefile, national coverage, ~954 MB zip for all of Ethiopia (clip to Bahir Dar after download)
- **Satellite imagery** — Sentinel-2, ESA/Copernicus — via Google Earth Engine (`COPERNICUS/S2_SR_HARMONIZED`) or https://dataspace.copernicus.eu — 10 m resolution, free, cloud-based, covers 2015 to present

## What I would build
A simple 2015 vs 2025 side-by-side (or swipe) map of Bahir Dar's built-up footprint, with the percentage growth in built-up area printed alongside it — a small, self-contained first output for the GeoDev Lab Africa repo.
