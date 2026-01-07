# Dataset Submission Instructions

This page describes how to contribute a new landslide or ground-failure dataset to the **CRESCENT Ground Failure Repository**. Contributions are community-driven and follow a transparent, reproducible workflow to ensure consistency, traceability, and appropriate attribution.

Please review the requirements and workflow below before preparing a submission.

---

## Dataset Requirements (Summary)

To be eligible for inclusion in the repository, submitted datasets must:

- Be primarily located within the **CRESCENT geographic footprint** (Cascadia and surrounding regions)
- Represent landslides or related ground-failure phenomena (e.g., debris flows, rockfalls, lateral spreading)
- Be associated with a **peer-reviewed publication, agency report, or citable data product**
- Have a **DOI or persistent identifier** for the original source
- Be distributable under terms that allow reuse and redistribution
- Preserve original attribution and scientific intent

The repository does **not** reinterpret or reclassify landslides scientifically; all transformations are limited to harmonization and documentation.

---

## Overview of the Processing Workflow

All datasets in the repository follow a two-stage processing pipeline:

1. **PreProcessing** – source-specific ingestion and normalization  
2. **PostProcessing** – cross-dataset harmonization and final schema alignment  

This workflow is implemented entirely in Jupyter notebooks and is designed to be reproducible and extensible.

If you are adding a new dataset, you will follow the same structure.

---

## Step 1: PreProcessing (Source-Specific)

Start by creating a new notebook in:

```
processing_notebooks/PreProcessing/
```

You can use existing notebooks as templates, such as:

- CGS example:  
  `processing_notebooks/PreProcessing/california_preprocessing.ipynb`

- Oregon example:  
  `processing_notebooks/PreProcessing/oregon_preprocessing.ipynb`

- Washington example:  
  `processing_notebooks/PreProcessing/washington_preprocessing.ipynb`

- Canada example:  
  `processing_notebooks/PreProcessing/canada_preprocessing.ipynb`

Your PreProcessing notebook should:

- Load the source data in its native format
- Convert it to a GeoPandas GeoDataFrame
- Reproject geometries to the repository CRS
- Clean invalid or empty geometries
- Preserve original attributes (do not drop information)
- Add required provenance fields (source, citation, DOI, agency)
- Export an intermediate GeoJSON for post-processing

This notebook should clearly document:
- Data source and download location
- Any assumptions or known limitations
- Decisions made during cleaning or normalization

---

## Step 2: PostProcessing (Harmonization)

Once your dataset is preprocessed, integrate it into the shared post-processing workflow located at:

```
processing_notebooks/PostProcessing/post_processing.ipynb
```

During this stage, your dataset will be:

- Mapped to the repository’s controlled vocabularies
- Aligned with the common attribute schema
- Augmented with derived fields used by the viewer
- Validated for geometry type and attribute completeness
- Exported as a final, standardized GeoJSON

### External Contextual Datasets

The post-processing workflow also integrates external contextual datasets used for analysis and visualization, including:

- **Rainfall data** (used to characterize precipitation-triggered landslides):  
  30 years average annual rainfall data from: 30-Year (1990-2019) Annual Average of DAYMET Precipitation and Temperature for North America https://doi.org/10.5066/P9E0JZ82


- **USGS ShakeMap products** (used for earthquake-triggered ground failure):  
  https://earthquake.usgs.gov/scenarios/eventpage/cszm9ensemble_se/shakemap/intensity

These datasets are *not* modified or redistributed, but are referenced during processing to derive standardized contextual attributes.

---

## Step 3: Final Review and Submission

Once you have produced a clean, standardized GeoJSON:

- Verify that the dataset loads correctly in the Ground Failure Viewer
- Confirm that all required metadata fields are populated
- Ensure attribution and citations are accurate
- Confirm licensing and redistribution terms

At this point, **do not open a pull request yet**.

---

## Contact and Submission

To finalize a submission, please contact the CRESCENT Ground Failure Repository team with:

- A short description of the dataset
- The associated publication or report DOI
- A link to the final processed GeoJSON
- Any notes on limitations or interpretation

Contact:

cascadiaquakes@uoregon.edu  

Cascadia Region Earthquake Science Center  

or open an issue in the repository to initiate the submission process.

The core team will review the dataset, coordinate final integration, and ensure proper credit before publication.

---

Thank you for contributing to the CRESCENT Ground Failure Repository and supporting open, reproducible hazards science.
