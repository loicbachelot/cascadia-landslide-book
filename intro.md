# CRESCENT Ground Failure Repository

---------------------
This Jupyter book is in support of the viewer available here: https://ground-failure.cascadiaquakes.org/

---------------------


The **CRESCENT Ground Failure Repository** is a community resource for the collection, documentation, and dissemination of landslide and ground-failure inventories within the Cascadia Subduction Zone and surrounding regions. The repository is designed to support reproducible hazards science by providing standardized access to curated datasets describing landslide occurrence, characteristics, and triggering conditions across multiple jurisdictions and event types.

This effort is part of the broader mission of the **Cascadia Region Earthquake Science Center (CRESCENT)** to advance understanding of earthquake-related and multi-hazard processes in the Pacific Northwest through open science, community data products, and shared cyberinfrastructure.

## Motivation

Landslide and ground-failure inventories are foundational datasets for studies of seismic hazard, earthquake-induced ground failure, rainfall-triggered landslides, infrastructure risk, and landscape evolution. In Cascadia, large earthquakes, intense precipitation, and complex geology combine to produce widespread slope instability, yet landslide data are often compiled independently by different agencies, researchers, and projects.

Over the past decade, advances in remote sensing, geospatial analysis, and data integration—including high-resolution lidar, satellite imagery, automated mapping approaches, and improved hazard modeling—have enabled the creation of increasingly detailed landslide inventories at local, regional, and national scales.


The CRESCENT Ground Failure Repository aims to provide:
- An openly accessible collection of curated landslide and ground-failure datasets,
- Consistent documentation describing data sources, methods, and limitations, and
- A visualization platform that enables interactive exploration, filtering, and download of standardized data products.

## Scope

The repository aims to be community based and is currently pre-populated with landslide inventories developed by state and provincial geological surveys (including CGS, DOGAMI, WADNR, and NRCan). These datasets are ingested, harmonized, and documented using a transparent preprocessing pipeline described in the {ref}preprocessing section of this book.

To be included in the repository, datasets must:
- Be primarily located within the **CRESCENT geographic footprint** (Cascadia and surrounding regions), and
- Be associated with a **peer-reviewed publication, agency report, or citable data product** with a DOI or persistent identifier.

## Repository Structure

Each dataset included in the repository consists of:
1. One or more downloadable data files (e.g., GeoJSON, CSV), and  
2. A corresponding **Jupyter Book page** describing the dataset provenance, methodology, spatial and temporal coverage, and scientific context.

Dataset description pages follow a standardized Markdown format to promote clarity and consistency while allowing contributors to document region-specific practices and interpretations.

## Visualization

Datasets hosted in this repository are integrated into the **CRESCENT Ground Failure Viewer**, which provides interactive visualization of landslides and ground-failure features across Cascadia. The viewer supports spatial filtering, attribute exploration, and data download, and is intended as a discovery and synthesis tool rather than a replacement for citation of original sources.

## Dataset formating

For a detailed description of dataset fields, classifications, and metadata conventions, please see the {ref}`Dataset-processing` section.

## Project Contacts

The CRESCENT Ground Failure Repository is developed and maintained by the CRESCENT cyberinfrastructure team in collaboration with state agencies, researchers, and the broader Cascadia hazards community. Individual datasets remain the intellectual property of their original authors and organizations.

**Amanda M. Thomas**  
Department of Earth and Planetary Sciences, University of California, Davis  

**William Marfo**  
Cascadia Region Earthquake Science Center  
Department of Earth and Planetary Sciences, University of California, Davis  

**Loïc Bachelot**  
Cascadia Region Earthquake Science Center  
Department of Earth Sciences, University of Oregon

## Acknowledgments

This project is supported by the **National Science Foundation** through the Cascadia Region Earthquake Science Center (CRESCENT).
