# Cobb County Green Structure Typology (Georgia, USA)

A county-wide spatial analysis in **QGIS** that classifies “green space” by **spatial structure** (patch size, shape, connectivity, fragmentation) rather than spectral greenness. The goal is interpretability and reproducibility under real-world public-data constraints.

**Study area:** Cobb County, Georgia (county-wide only)  
**CRS:** EPSG:2240 — NAD83 / Georgia West (US survey feet)  
**Area units:** Acres  
**Software:** QGIS only (no proprietary extensions)

---

## Project Question

**Core research question:**  
Where does green space in Cobb County represent structurally complex, ecologically meaningful vegetation versus human-maintained or residual green cover?

This project treats “greenness” as context-dependent. It avoids over-claiming ecological outcomes and instead focuses on **spatial indicators** that are legible, auditable, and mappable.

---

## Methodological Philosophy

- Emphasizes **spatial structure** over spectral indices
- Treats “green” as ambiguous: the same land cover can represent different ecological roles depending on configuration
- Uses **patch size, shape, fragmentation, and connectivity** as interpretable indicators
- Avoids causal claims about habitat quality or biodiversity
- Prioritizes reproducibility: decisions are documented and outputs are traceable

---

## Green Structure Typology (Locked)

1. **Core Patches** — large contiguous green areas  
2. **Edge Patches** — medium patches with high edge-to-area ratios  
3. **Corridors** — linear green features (riparian buffers, greenways, ROWs)  
4. **Stepping Stones** — small isolated patches  
5. **Residual Green** — very small or thin green fragments  

---

## Data Sources (Public)

- U.S. Census **TIGER/Line** (county boundaries)
- **NLCD 2021 Land Cover** (MRLC)
- USGS / public hydrography (where relevant for interpreting corridors)

See `data/raw/README.md` for source notes and handling constraints.

---

## Deliverables (No invented results)

This repository contains the structure and artifacts needed for the following deliverables:

- Green vs Non-Green mask
- Green Structure Typology map
- Summary tables (acres and percent)
- Short written report (DOCX → PDF)
- Portfolio-ready figures

---

## Repository Organization

- `qgis/` — QGIS project file(s), styles, and model artifacts supporting reproducibility  
- `data/`  
  - `raw/` — intentionally empty (documented); raw inputs stored locally  
  - `interim/` — scratch outputs used during processing (optional)  
  - `processed/` — selected processed layers used to generate figures/tables  
- `outputs/` — exported maps and final tables intended for viewing/sharing  
- `docs/` — report (DOCX/PDF) and figure set for portfolio presentation  

---

## Limitations

- **Land cover generalization:** NLCD is categorical and resolution-limited; small features and mixed pixels can blur patch boundaries.  
- **Structure ≠ ecology:** patch geometry and connectivity are proxies and do not directly measure habitat quality, biodiversity, or ecological function.  
- **Edge definition sensitivity:** results depend on threshold choices (e.g., minimum patch size, corridor width criteria, edge-to-area cutoffs).  
- **Temporal mismatch:** datasets may not align perfectly in time; interpretation is descriptive rather than causal.

---

## Future Improvements (Constrained and honest)

- Parameter sensitivity checks (how typology shifts across thresholds)
- Optional comparative layer: NDVI **only** as a secondary reference (not a primary classifier)
- Incorporate additional public layers for interpretive context (e.g., parks, zoning, protected areas) without changing core typology logic
- Add a reproducible QGIS Model Builder pipeline for the full typology workflow

---

## Status

- Typology definitions locked
- County-wide scope locked
- Outputs and tables will be added as processing is completed (no placeholder results)

---

## License

Add an explicit license before sharing broadly (see `LICENSE`).
