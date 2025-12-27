# Cobb County Green Structure Typology
🔗 Portfolio hub: https://walkerwest8-blip.github.io
## Overview
This project develops a **structural typology of green space** for Cobb County, Georgia using QGIS and publicly available land cover data. Rather than relying on vegetation indices (e.g., NDVI), the analysis focuses on **spatial structure**—patch size, shape, and linearity—to understand how green space is organized and connected across a suburban landscape.

The result is a reproducible, county-wide classification that highlights the dominance of **linear corridors** over compact green cores.

---

## Study Area
- **Location:** Cobb County, Georgia (USA)
- **Extent:** County-wide
- **Coordinate Reference System:**  
  NAD83 / Georgia West (EPSG:2240, US survey feet)

---

## Data Sources
All data used in this project are publicly available:

- **NLCD 2023 Land Cover**  
  Multi-Resolution Land Characteristics (MRLC)
- **County Boundaries**  
  U.S. Census Bureau TIGER/Line

Raw national datasets are not included in this repository to keep it lightweight and reproducible.

---

## Method Summary
1. NLCD land cover was clipped to the Cobb County boundary.
2. Vegetated land cover classes (forest, shrub, grassland, pasture/hay, wetlands) were selected to create a binary green mask.
3. Green areas were polygonized into individual patches.
4. Patch area (acres) and shape metrics were calculated.
5. Patches were classified using an **area-based typology**:
   - Residual (< 1 acre)
   - Stepping Stone (1–5 acres)
   - Edge Patch (5–40 acres)
   - Core Patch (> 40 acres)
6. A compactness-based shape index was used to identify **corridor features**.
7. Corridors override area-based classes in the final typology.
8. Large corridors (> 40 acres) were flagged as **core-but-linear** features for interpretation.

---

## Final Structural Classes
- **Corridor**
- **Edge Patch**
- **Stepping Stone**
- **Residual Green**

No compact core patches were identified after accounting for corridor geometry.

---

## Key Findings
- Green space in Cobb County is **highly fragmented** by count, with thousands of small residual patches.
- The majority of total green area is contained within **elongated corridor features**, not compact blocks.
- Twelve large, linear features exceed the core size threshold (>40 acres) but remain structurally corridor-like.
- Connectivity in the county is therefore maintained primarily through **riparian systems and linear greenways**, rather than intact core reserves.

---

## Repository Contents

### Maps
- `maps/Cobb_GreenStructure_Typology.png`  
- `maps/Cobb_GreenStructure_Typology.pdf`

### Tables
- `tables/green_structure_by_class.csv`  
  Summary of patch counts and total area by structural class.
- `tables/core_linear_summary.csv`  
  Summary of large corridor features functioning as de facto cores.

### QGIS Project
- `qgis/Cobb_GreenStructure.qgz`  
  Preserves full workflow context, symbology, and analytical fields.

---

## Limitations
- Structural classification does not directly measure ecological quality or habitat value.
- Results are dependent on NLCD thematic resolution and classification accuracy.
- Corridors are identified using geometric criteria only, without network or flow modeling.

---

## Author
Analysis and cartography by **[Your Name]**

---

## License
This project is intended for educational and portfolio use. Data sources retain their original licenses.
