# Project Status — Cobb County Green Structure Typology

**Status:** Complete  
**Study area:** Cobb County, Georgia (county-wide)  
**CRS:** EPSG:2240 — NAD83 / Georgia West (US survey feet)  
**Area units:** Acres  
**Software:** QGIS (public data only)

---

## Project Summary

This project classifies green space in Cobb County, Georgia based on **spatial structure rather than spectral greenness**. The analysis emphasizes patch size, shape, and linearity to distinguish between compact green areas and corridor-dominated vegetation patterns under real-world public-data constraints.

---

## Completed Analysis

### Study Area and Data
- Defined a county-wide study area for Cobb County, Georgia
- Locked project CRS to EPSG:2240 to support accurate area calculations
- Clipped NLCD 2023 land cover data to the study extent
- Created a binary green mask distinguishing vegetated and non-vegetated land cover

### Patch-Based Structural Analysis
- Polygonized green space into approximately **5,800 individual patches**
- Calculated patch areas in acres using projected geometry
- Applied an area-based typology:
  - **Residual Green:** < 1 acre
  - **Stepping Stone:** 1–5 acres
  - **Edge Patch:** 5–40 acres
  - **Core Patch:** > 40 acres

### Corridor Detection and Refinement
- Applied shape-based metrics (compactness / linearity) to identify corridor features
- Corridor classification overrides area-based classes where geometry indicates linear structure
- Identified **12 large, linear features (> 40 acres)** reclassified as corridors
- Final structural classes:
  - Corridor
  - Edge Patch
  - Stepping Stone
  - Residual Green

### Outputs
- Summary tables reporting patch count and total area by structural class
- Final typology map exported to PNG and PDF formats
- QGIS project file preserving full workflow context

---

## Key Result

Cobb County’s green structure is **dominated by linear corridors rather than compact core patches**. Connectivity is primarily expressed through riparian systems and greenways, with few intact, block-like green areas present at the county scale.

This result reflects **spatial configuration**, not ecological quality, and is interpreted accordingly.

---

## Repository Notes

This repository includes processed datasets, summary outputs, and documentation required to review and reproduce the analysis logic. Large raw datasets and intermediate processing layers are intentionally excluded and are publicly reproducible from documented sources.


This finding reflects **structural configuration**, not ecological quality, and is interpreted accordingly.
