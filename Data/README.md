# Data

## Overview
This directory contains the spatial datasets used in the study **"Unmanaged waste as an outcome of expanding sub-Saharan African cities"**, published in *npj Urban Sustainability*.
The datasets cover ten sub-Saharan African cities: Abidjan, Accra, Dakar, Freetown, Johannesburg, Kampala, Kinshasa, Lagos, Maputo, and Nairobi.
The data include mapped unmanaged waste site polygons, site locations and areas, and gridded urban covariates with corresponding waste burden values. These datasets support the spatial statistical modelling and neighbourhood level analyses presented in the manuscript.

## Data collection and preparation
Unmanaged waste sites were initially identified using a previously developed multi-model detection framework applied to Sentinel-2 satellite imagery. All detected sites were individually verified, and their boundaries manually delineated using high-resolution Google Earth satellite imagery.
Waste sites were mapped between January and March 2024. The resulting site locations and polygons were collected and curated specifically for this study rather than obtained from an existing waste site database.
Urban predictor datasets were compiled from multiple sources, harmonised to a common spatial resolution of 30 m, and temporally aligned where possible to minimise inconsistencies arising from urban change.

## Directory structure

### 1. `Waste_polygons/`
Contains the mapped unmanaged waste site boundaries for each of the ten cities in 2024.

- **Format:** ESRI Shapefile (`.shp` and associated files).
- **Geometry:** Polygon.
- **Contents:** Spatial footprints of individually verified and manually delineated unmanaged waste sites.

These polygons represent the geographical extent of mapped waste accumulations and can be used for spatial analysis, visualisation, and calculation of site areas.

### 2. `Site_locations/`
Contains city-specific CSV files describing the location and size of individual unmanaged waste sites.
Each record corresponds to an individual mapped site and includes:

- **Latitude:** Geographical latitude of the site centroid.
- **Longitude:** Geographical longitude of the site centroid.
- **Site area:** Mapped waste site footprint area, expressed in square metres (m²).

These datasets provide the point locations and associated site sizes used in the spatial point process analyses.

### 3. `City_grids_covariates/`
Contains city-specific gridded datasets used for spatial modelling and analysis.
Each record represents a spatial grid location at approximately 30 m resolution, with associated urban predictor values and a continuous unmanaged waste burden value (dependent variable).
The urban covariates represent five broad dimensions:

| Predictor domain | Variables |
|---|---|
| Demographic characteristics | Population density, proportion of population under 18 |
| Economic conditions | Relative Wealth Index (RWI), night-time light radiance (NTL) |
| Urban informality | Slum likelihood |
| Accessibility | Composite infrastructure accessibility index, distances to secondary and tertiary roads |
| Built morphology | Distance to open space, orientation dispersion, building ordering (Clark–Evans R), building footprint area, building spacing, composite built environment index |

The composite accessibility and built environment indices were constructed using Principal Component Analysis (PCA).
The gridded datasets additionally contain the **continuous waste burden (DV)**, representing the spatial influence of mapped waste sites based on their area, proximity, and overlapping effects.
These datasets form the primary inputs for the analyses of spatial associations between urban characteristics and unmanaged waste.

## Data usage
The datasets are provided to support reproducibility and further spatial analysis of unmanaged waste across urban environments.

Users should note that:

1. **Spatial reference systems:** Coordinate reference systems should be verified before performing distance, area, or spatial overlay operations.
2. **Spatial resolution:** The covariate datasets were harmonised to a 30 m grid. Individual observations should be interpreted in the context of this spatial resolution.
3. **Variable definitions:** Covariate names and units should be checked against the corresponding analysis scripts in the `Code/` directory.
4. **Waste burden:** The continuous dependent variable represents modelled spatial waste burden rather than directly measured waste mass or volume.
5. **Temporal coverage:** The mapped waste sites represent conditions observed during January to March 2024. Urban covariates were temporally aligned where possible.

## Related code and results

The datasets are used in the analytical scripts available in the repository's `Code/` directory:

- `Log-Gaussian-Cox.Rmd`: Spatial statistical modelling of waste site occurrence and size.
- `Exposure_surface_spatial_analysis.ipynb`: Analysis of continuous waste burden, spatial clustering, and associations with urban covariates.

Associated model outputs and figures are available in the `Results/` and `Figures/` directories, respectively.

For further information on data sources, predictor construction, and analytical methodology, refer to the Methods and Supplementary Information of the associated publication.

