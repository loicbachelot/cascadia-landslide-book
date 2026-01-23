# Cascadia Ground Failure Data Repository

[![Build Jupyter Book](https://github.com/cascadiaquakes/cascadia-landslide-book/actions/workflows/deploy-book.yml/badge.svg)](https://github.com/cascadiaquakes/cascadia-landslide-book/actions/workflows/deploy-book.yml)

📘 **Documentation (Jupyter Book):** https://cascadiaquakes.github.io/cascadia-landslide-book  
🌐 **Interactive Viewer:** https://ground-failure.cascadiaquakes.org/

---

This repository supports the **collection, harmonization, and preparation of landslide and ground-failure inventories** for the Cascadia region (California, Oregon, Washington, and British Columbia). It underpins the **CRESCENT Ground Failure Repository** and associated web viewers by providing transparent, reproducible data-processing workflows.

The repository contains:
- Jupyter notebooks documenting **data acquisition, preprocessing, harmonization, and enrichment**
- Standardized outputs (GeoJSON / CSV) suitable for visualization, analysis, and downstream applications
- A **Jupyter Book** that documents the full processing pipeline and serves as the primary reference for contributors

---

## Documentation

The full, curated documentation, including step-by-step preprocessing examples and submission instructions is available via the **Jupyter Book**:

👉 https://cascadiaquakes.github.io/cascadia-landslide-book

If you are new to the project or planning to contribute data, **start with the book**.

---

## Data Acquisition

Before running any preprocessing notebooks, download the required datasets from their official sources and place them in a local `DATA/` directory (not tracked by git).

### Landslide Inventories

- **Oregon**  
  Statewide Landslide Information Database for Oregon (SLIDO)  
  https://www.oregon.gov/dogami/slido/Pages/data.aspx

- **Washington**  
  Washington Geological Survey – Landslide Hazard Program  
  https://dnr.wa.gov/washington-geological-survey/geologic-hazards-and-environment/landslides

- **California**  
  California Geological Survey – Landslide Inventory and Deep-Seated Landslide Susceptibility Map  
  https://maps.conservation.ca.gov/cgs/lsi/

- **British Columbia (regional example)**  
  Landslide inventory map of the Valemount area  
  https://ostrnrcan-dostrncan.canada.ca/entities/publication/405661b8-7bd8-49d0-8f03-f9bac9aa7c52

- **Canada (national)**  
  Preliminary Canadian Landslide Database  
  https://doi.org/10.5281/zenodo.7089351

---

## Ancillary Hazard Datasets

### Seismic Shaking (USGS ShakeMap)

For earthquake-triggered ground-failure metrics (PGA, PSA, MMI, etc.), download the **ShakeMap XML Grid File** from:

- USGS M9.0 Cascadia Scenario Earthquake  
  https://earthquake.usgs.gov/scenarios/eventpage/cszm9ensemble_se/shakemap/intensity

Place the downloaded `grid.xml` file in the `DATA/` directory.

### Rainfall Data

Long-term precipitation metrics are derived from:

- **30-Year (1990–2019) Annual Average DAYMET Precipitation for North America**  
  https://doi.org/10.5066/P9E0JZ82

These data are used during post-processing to associate landslides with climatological rainfall statistics.

---

## Repository Structure

```
.
├── processing_notebooks/
│   ├── ExploratoryDataAnalysis/     # Initial exploration (not part of the book)
│   ├── PreProcessing/               # Source-specific ingestion & cleaning
│   ├── PostProcessing/              # Harmonization, IDs, hazard attribution
│   └── postGIS/                     # Optional database workflows
│
├── datasets_description/            # Supporting metadata and notes
├── static_tiling/                   # Vector tile generation pipelines
│
├── intro.md                         # Jupyter Book landing page
├── processing.md                    # Processing overview (book)
├── submission_instructions.md       # Contribution guide (book)
├── _toc.yml                         # Jupyter Book table of contents
├── _config.yml                      # Jupyter Book configuration
└── README.md
```

---

## Processing Workflow

1. **Exploratory Data Analysis**  
   Initial inspection of raw inventories (formats, attributes, spatial coverage).

2. **PreProcessing**  
   - Ingest raw datasets  
   - Normalize geometries and coordinate reference systems  
   - Map source attributes to a common schema

3. **PostProcessing**  
   - Assign globally unique landslide identifiers  
   - Integrate seismic shaking metrics (ShakeMap)  
   - Associate rainfall and other environmental parameters  
   - Produce standardized GeoJSON / CSV outputs

4. **(Optional) Vector Tile Generation**  
   Convert processed GeoJSON into vector tiles for efficient web visualization.

---

## Requirements

### Core Python Packages

- geopandas  
- numpy  
- pandas  
- seaborn  
- fiona  
- contextily  

Install with:

```bash
pip install geopandas numpy pandas seaborn fiona contextily
```

### Vector Tile Generation (optional)

**Tippecanoe**

```bash
# macOS (Homebrew)
brew install tippecanoe

# Ubuntu / Debian
git clone https://github.com/mapbox/tippecanoe.git
cd tippecanoe
make -j
sudo make install
```

---

## Contributing Data

If you would like to contribute a new landslide inventory:

1. Follow the preprocessing examples in the **Jupyter Book**
2. Produce a clean, standardized GeoJSON output
3. Review the **Submission Instructions** page in the book
4. Contact the CRESCENT Ground Failure team to coordinate inclusion

---

## Acknowledgments

This work is developed as part of the **Cascadia Region Earthquake Science Center (CRESCENT)** and is supported by the **National Science Foundation**.  
All original datasets remain the intellectual property of their respective agencies and authors.
