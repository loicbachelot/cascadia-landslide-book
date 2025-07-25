# Cascadia Landslide Database Viewer

A project for collecting, processing, and visualizing landslide data for the Cascadia region (California, Oregon, Washington, and British Columbia).

## Project Structure

### 1. ExploratoryDataAnalysis
Contains notebooks for initial analysis of data from each source.

### 2. Data Acquisition
Before processing, download required datasets from the official sources and place them in a 'DATA' directory:
- Oregon: [Statewide Landslide Information Database for Oregon (SLIDO)](https://www.oregon.gov/dogami/slido/Pages/data.aspx)
- Washington: [WGS Landslide Hazard Program](https://dnr.wa.gov/washington-geological-survey/geologic-hazards-and-environment/landslides)
- California: [California Landslide Inventory and Deep Landslide Suspectibility Map](https://maps.conservation.ca.gov/cgs/lsi/)
- British Columbia: [Landslide inventory map of the Valemount area, British Columbia](https://ostrnrcan-dostrncan.canada.ca/entities/publication/405661b8-7bd8-49d0-8f03-f9bac9aa7c52)
- Canada: [Preliminary Canadian Landslide Database](https://data.niaid.nih.gov/resources?id=zenodo_7089351)

### 3. PreProcessing
Contains notebooks for preprocessing different datasets.

Processed data is saved in the `PreprocessedDataSets` directory

### 3. CombineDataSets
Contains notebooks to combine datasets from different regions.

## Workflow
1. Exploratory Data Analysis
2. Preprocessing
3. Combine Datasets

## Requirements
To run the notebooks in this repository, you need:
- geopandas
- numpy
- seaborn
- fiona
- contextily (For map overlays in visualizations)

## Installation
```bash
pip install geopandas numpy seaborn fiona contextily
```