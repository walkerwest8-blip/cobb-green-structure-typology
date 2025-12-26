# Project Status — Cobb County Green Structure Typology

**Status:** Active  
**Current Phase:** Phase 1 — Patch-Based Typology (in progress)

---

## Overview

This project is a county-wide spatial analysis conducted in QGIS using publicly available data. It classifies green space in Cobb County, Georgia based on **spatial structure** rather than spectral greenness, emphasizing interpretability, reproducibility, and analytical restraint.

---

## Completed Work

### Project Setup
- Defined a county-wide study area: **Cobb County, Georgia**
- Locked coordinate reference system: **EPSG:2240 (NAD83 / Georgia West, US survey feet)**
- Established a clean, professional folder structure for reproducible GIS work
- Created a project README defining scope, intent, and limitations

---

### Data Intake (Public Sources Only)
- Downloaded U.S. Census TIGER/Line nationwide county boundaries
- Isolated and exported Cobb County as the authoritative working boundary
- Downloaded NLCD 2023 land cover (CONUS) and clipped to Cobb County
- Maintained strict separation between raw data and working datasets

---

### Analytical Foundation
- Designed a **Green Structure Typology** focused on spatial configuration rather than NDVI
- Defined “green space” using NLCD classes:
  - Forest
  - Shrubland
  - Grassland
  - Pasture/Hay
  - Wetlands
- Explicitly excluded developed open space and low-intensity development to avoid lawn bias

---

### Raster → Vector Workflow
- Created a binary **Green Mask** raster:
  - 1 = green
  - 0 = non-green
- Polygonized the green mask into **5,855 individual green patches**
- Converted raster outputs into clean vector datasets for structural analysis

---

### Patch Metrics
- Calculated patch area in **acres** using the project CRS
- Observed maximum patch size ≈ **143 acres**, confirming suburban-scale structure

---

### Typology Classification (Area-Based — Locked)
Applied a first-pass structural classification based on patch area:

- **Residual Green:** < 1 acre
- **Stepping Stones:** 1–5 acres
- **Edge Patches:** 5–40 acres
- **Core Patches:** > 40 acres

Each patch is now tagged with a `patch_class` attribute.

---

## Tangible Artifacts (Current)

The following datasets currently exist and represent real analytical progress:

- `cobb_boundary.gpkg` — authoritative study boundary
- `nlcd_2023_cobb.tif` — clipped land cover raster
- `green_mask_cobb.tif` — binary green / non-green raster
- `green_patches.gpkg` — vector dataset containing:
  - Patch area (acres)
  - Structural class (`patch_class`)
- QGIS project file preserving full workflow context

---

## What Is Uploaded to GitHub (Portfolio-Facing)

### Included
- Project README documenting scope and methodology
- QGIS project file (`.qgz`)
- Processed, county-specific datasets only
- This project status log

### Intentionally Excluded
- Large raw CONUS datasets
- Temporary or intermediate processing files
- Any data not clipped to Cobb County

All excluded datasets are publicly available and reproducible from documented sources.

---

## Next Steps (Not Yet Completed)
- Visual validation of patch classes (spatial sanity checks)
- Identification of corridors using shape and linearity metrics (not area alone)
- Summary tables (area and count by patch class)
- Final map layouts and short interpretive report (DOCX → PDF)

---

## One-Sentence Framing

This project classifies green space in Cobb County, Georgia based on spatial structure rather than greenness indices, highlighting where vegetation represents ecologically meaningful structure versus fragmented or human-maintained green cover.
