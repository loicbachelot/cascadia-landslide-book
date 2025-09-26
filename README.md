# Cascadia Landslide Database Viewer

A project for collecting, processing, and visualizing landslide data for the Cascadia region (California, Oregon, Washington, and British Columbia).

## Data Acquisition
Before processing, download required datasets from the official sources and place them in a 'DATA' directory:
- Oregon: [Statewide Landslide Information Database for Oregon (SLIDO)](https://www.oregon.gov/dogami/slido/Pages/data.aspx)
- Washington: [WGS Landslide Hazard Program](https://dnr.wa.gov/washington-geological-survey/geologic-hazards-and-environment/landslides)
- California: [California Landslide Inventory and Deep Landslide Suspectibility Map](https://maps.conservation.ca.gov/cgs/lsi/)
- British Columbia: [Landslide inventory map of the Valemount area, British Columbia](https://ostrnrcan-dostrncan.canada.ca/entities/publication/405661b8-7bd8-49d0-8f03-f9bac9aa7c52)
- Canada: [Preliminary Canadian Landslide Database](https://data.niaid.nih.gov/resources?id=zenodo_7089351)

For ShakeMap intensity value download the XML Grid File from [USGS M 9.0 Scenario Earthquake - M9.0 Cascadia event page](https://earthquake.usgs.gov/scenarios/eventpage/cszm9ensemble_se/shakemap/intensity). Place the grid.xml file inside the DATA directory

## Project Structure

### 1. ExploratoryDataAnalysis
Contains notebooks for initial analysis of data from each source.

### 2. PreProcessing
Contains notebooks for preprocessing different datasets.

Processed data is saved in the `PreprocessedDataSets` directory


### 3. CombineDataSets
Contains notebooks to combine datasets from different regions.

### 4. PostProcessing
Adds Unique Identifiers to each landslide and Integrates USGS ShakeMap intensity values to extract PGA, PSA, and other seismic parameters for each landslide.

### 5. VectorTilesPipeline
Converts processed GeoJSON landslide data into optimized vector tiles using Tippecanoe for efficient web visualization in Cesium viewer. Creates MBTiles with proper zoom levels and serves them via tileserver-gl Docker container.

## Workflow
1. Exploratory Data Analysis
2. Preprocessing
3. Combine Datasets
4. PostProcessing
5. Vector Tiles Pipeline

## Requirements
To run the notebooks in this repository, you need:
- geopandas
- numpy
- seaborn
- fiona
- contextily (For map overlays in visualizations)
- tippecanoe (Command-line tool for creating vector tiles from GeoJSON data)

## Installation
### Python packages
```bash
pip install geopandas numpy seaborn fiona contextily
```

### Tippecanoe (for vector tiles)
```bash
# macOS (using Homebrew)
brew install tippecanoe

# Ubuntu/Debian
git clone https://github.com/mapbox/tippecanoe.git
cd tippecanoe
make -j
make install
```