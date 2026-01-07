(dataset-processing)=
# Dataset Processing and Harmonization

Landslide inventories included in the CRESCENT Ground Failure Repository originate from multiple state and provincial geological surveys and are produced using different mapping practices, classification schemes, spatial representations, and attribute conventions. As a result, raw inventories are not directly comparable across regions without careful preprocessing.

To address this, all datasets in the repository are passed through a transparent, reproducible processing pipeline implemented as a series of Jupyter notebooks. These notebooks document how each source inventory is ingested, cleaned, standardized, and prepared for visualization and distribution.

The processing workflow is divided into two main stages:

- **PreProcessing**: source-specific ingestion and normalization  
- **PostProcessing**: cross-dataset harmonization and final schema alignment  

All processing notebooks are provided in full to support reproducibility and reuse.

---

## PreProcessing

The **PreProcessing** stage focuses on converting each source inventory from its native format into a common geospatial representation while preserving the original information content and attribution.

Because each agency distributes data differently, preprocessing steps are necessarily dataset-specific. Typical tasks performed at this stage include:

- Downloading or loading source data (e.g., shapefiles, geodatabases, CSVs)
- Converting data into GeoPandas-compatible formats
- Reprojecting geometries to a common coordinate reference system
- Cleaning invalid or empty geometries
- Renaming and documenting original attribute fields
- Adding required identifiers and provenance metadata

Each source inventory has its own dedicated preprocessing notebook:

- **California Geological Survey (CGS)**  
  `processing_notebooks/PreProcessing/01_cgs_download_to_geopandas.ipynb`

- **Washington Department of Natural Resources (WADNR)**  
  `processing_notebooks/PreProcessing/washington_preprocessing.ipynb`

- **Oregon DOGAMI**  
  `processing_notebooks/PreProcessing/oregon_preprocessing.ipynb`

- **Natural Resources Canada (NRCan)**  
  `processing_notebooks/PreProcessing/canada_preprocessing.ipynb`

These notebooks document source-specific assumptions, data limitations, and processing choices and should be read alongside the resulting datasets.

> **Note:** PreProcessing does *not* reinterpret landslide classifications or alter scientific meaning. The goal is normalization and documentation, not reanalysis.

---

## PostProcessing

The **PostProcessing** stage applies once all source inventories have been individually preprocessed into a consistent geospatial format.

At this stage, datasets are combined and harmonized to support region-wide analysis and visualization. Typical post-processing steps include:

- Mapping source-specific classifications to a common controlled vocabulary
- Standardizing attribute names, data types, and units
- Adding derived fields used by the Ground Failure Viewer
- Enforcing a shared schema across all inventories
- Validating geometry types and attribute completeness
- Exporting final, standardized data products for distribution

PostProcessing is implemented in a shared notebook:

- **Unified Post-Processing and Harmonization**  
  `processing_notebooks/PostProcessing/post_processing.ipynb`

This separation ensures that:
- Source-specific logic remains clearly isolated, and
- Cross-dataset decisions are applied consistently and transparently.

---

## Reproducibility and Extension

All processing notebooks are version-controlled and designed to be re-run as source datasets evolve or new inventories are added. Contributors who wish to add new datasets are encouraged to follow the same two-stage structure:

1. Create a new **PreProcessing** notebook for the source dataset  
2. Integrate the output into the existing **PostProcessing** workflow  

This design allows the repository to grow while maintaining consistency, traceability, and scientific integrity.
