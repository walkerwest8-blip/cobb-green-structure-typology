# Project Update — Cobb County Green Structure Typology

**Project status:** Complete  
**Scope:** County-wide (Cobb County, Georgia)  
**Software:** QGIS (public data only)  
**CRS:** EPSG:2240 — NAD83 / Georgia West (US survey feet)  
**Area units:** Acres

---

## Summary

This project classifies green space in Cobb County, Georgia based on **spatial structure** rather than spectral greenness. Using patch size, shape, and linearity metrics, the analysis distinguishes between corridors and fragmented green patches to better understand how vegetated space is organized at the county scale.

---

## Completed Analysis

### Data Preparation
- Defined a county-wide study area (Cobb County, GA)
- Locked project CRS to EPSG:2240 for consistent area calculations
- Clipped NLCD 2023 land cover to the study area
- Created a binary green mask (vegetated vs non-vegetated)

### Structural Patch Analysis
- Polygonized green space into approximately **5,800 individual patches**
- Calculated patch areas in acres using projected geometry
- Applied an area-based typology:
  - Residual Green (< 1 acre)
  - Stepping Stone (1–5 acres)
  - Edge Patch (5–40 acres)
  - Core Patch (> 40 acres)

### Corridor Identification
- Applied shape-based metrics (compactness/linearity) to detect corridors
- Corridors override area-based classes where geometry indicates linear structure
- Identified **12 large “core-but-linear” features** (> 40 acres) reclassified as corridors

### Final Structural Classes
- Corridor
- Edge Patch
- Stepping Stone
- Residual Green

### Outputs
- Summary tables (patch count and total area by class)
- Final typology map exported to PNG and PDF

---

## Key Result

Cobb County’s green structure is **dominated by linear corridors rather than compact core patches**. Connectivity is primarily expressed through riparian systems and greenways, with few intact, block-like green areas remaining at the county scale.

This finding reflects **structural configuration**, not ecological quality, and is interpreted accordingly.
