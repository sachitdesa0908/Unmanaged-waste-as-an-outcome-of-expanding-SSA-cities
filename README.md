# Unmanaged waste as an outcome of expanding sub-Saharan African cities

## Overview
This repository contains the data, code, model outputs, and figures associated with the research paper **"Unmanaged waste as an outcome of expanding sub-Saharan African cities"**, published in *npj Urban Sustainability*.
The study examines the spatial distribution of unmanaged waste across ten cities in sub-Saharan Africa, investigating how urban development, infrastructure, population distribution, and socioeconomic conditions influence the presence and accumulation of unmanaged waste.
The repository provides the underlying waste site data, urban covariates, spatial modelling scripts, and analytical outputs to support the transparency, reproducibility, and further application of the research.

## Study description
The study covers ten cities across sub-Saharan Africa: Abidjan, Accra, Dakar, Freetown, Johannesburg, Kampala, Kinshasa, Lagos, Maputo, and Nairobi.
Unmanaged waste sites were mapped for 2024, with their geographical locations and spatial footprints used to characterise the distribution and concentration of waste across urban environments. These observations were combined with spatially explicit indicators of urban development, infrastructure accessibility, population distribution, and socioeconomic conditions.
The analysis employs **Log Gaussian Cox Process (LGCP) models** to investigate the spatial associations between urban characteristics and both waste site occurrence and site size. A continuous waste exposure surface was also generated to represent the spatial influence of mapped waste sites, accounting for their size, proximity, and overlapping influence.
Together, these analyses examine how urban conditions shape the spatial distribution of unmanaged waste and identify patterns relevant to urban planning, waste management, and environmental sustainability.

## Repository structure
The repository is organised into four main directories:

### 1. `Code/`
Contains the scripts used for the spatial modelling and analysis:
- **LGCP modelling:** R scripts developed in RStudio for fitting and evaluating Log Gaussian Cox Process models, including screening and joint models of waste site occurrence and size.
- **Exposure surface generation:** Python scripts used to generate continuous spatial exposure surfaces from mapped waste sites, accounting for site area and distance.

### 2. `Data/`
Contains the spatial datasets and covariates used in the study:
- **Waste site polygons:** Shapefiles representing the mapped spatial footprints of unmanaged waste sites across the ten cities in 2024.
- **`Site_locations/`:** City-specific CSV files containing the latitude, longitude, and mapped area of individual waste sites.
- **`City_grids_covariates/`:** City-specific gridded datasets containing urban covariates and the corresponding continuous waste exposure values (dependent variable) at each grid location.

The waste site locations and polygons were specifically collected and curated for this study rather than obtained from an existing waste site database.

### 3. `Figures/`
Contains the spatial maps and figures associated with the manuscript:
- **City maps:** Maps showing the geographical distribution and relative size of unmanaged waste sites in relation to blue and green urban spaces.
- **`Figure_Manuscripts/`:** Figures generated for the manuscript, including visualisations of waste site distributions, spatial modelling results, and relationships between urban characteristics and unmanaged waste.

### 4. `Results/`
Contains the outputs of the spatial statistical analyses:
- **`LGCP/`:** Results from the screening and joint LGCP models, including estimated relationships between urban predictors and unmanaged waste site occurrence and size.
These outputs support the statistical findings and interpretations presented in the manuscript.

## Data availability
The unmanaged waste site locations and polygons were collected and curated specifically for this study and were not sourced from an existing waste site dataset.
The resulting spatial datasets, associated urban covariates, analysis scripts, model outputs, and figures are made available through this repository to support reproducibility and further research.
The waste site data represent mapped unmanaged waste accumulations as well as formal and managed municipal disposal facilities. The study, however, was primarily concerned with unmanaged waste. 

## Methodology and reproducibility
The analysis combines spatially explicit waste site observations with gridded urban covariates to examine the relationships between urbanisation and unmanaged waste.
The principal analytical components are:

1. **Waste site mapping:** Identification and delineation of unmanaged waste sites across the ten study cities.
2. **Exposure surface generation:** Construction of a continuous spatial representation of waste burden based on site area, proximity, and overlapping spatial influence.
3. **Spatial statistical modelling:** Application of LGCP models to investigate the associations between urban conditions and waste site occurrence and size.
4. **Model screening and evaluation:** Assessment of individual predictors and joint model specifications to identify the urban characteristics most strongly associated with unmanaged waste.
5. **Visualisation:** Generation of spatial maps and statistical figures to communicate the geographical patterns and modelling results.

### Software and requirements
The analyses were conducted using:
- **R / RStudio:** Spatial statistical modelling and LGCP analysis.
- **Python:** Spatial data processing and continuous exposure surface generation.
- **GIS software:** Spatial data preparation, inspection, and mapping.

The relevant scripts are provided in the `Code/` directory. Users should review the input file paths, data dependencies, and software packages specified within each script before execution.

## Citation
If you use the data, code, or results from this repository, please cite the associated publication:
**[Full author list] ([Year]).** Unmanaged waste as an outcome of expanding sub-Saharan African cities. *npj Urban Sustainability*. [DOI]

Repository: [Unmanaged-waste-as-an-outcome-of-expanding-SSA-cities](https://github.com/sachitdesa0908/Unmanaged-waste-as-an-outcome-of-expanding-SSA-cities)

## Contact
For questions regarding the datasets, analytical methods, or reproducibility of the study, please contact:

**Sachit Desa**  
University of Manchester  
[sachit.desa@manchester.ac.uk]
