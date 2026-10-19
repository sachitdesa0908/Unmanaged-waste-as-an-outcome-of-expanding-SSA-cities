# Code

## Overview

This directory contains the analytical scripts associated with the study **"Unmanaged waste as an outcome of expanding sub-Saharan African cities"**, published in *npj Urban Sustainability*.
The scripts support two principal components of the analysis: spatial statistical modelling of unmanaged waste site occurrence and size, and neighbourhood level analysis of continuous waste burden and its associations with urban characteristics.
The code was developed for the ten study cities and is provided to support reproducibility, methodological transparency, and adaptation to other urban environments.

## Code descriptions

### 1. `Log-Gaussian-Cox.Rmd`
**Language:** R  
**Environment:** RStudio

This R Markdown file implements Log Gaussian Cox Process (LGCP) models to investigate how urban characteristics are associated with the spatial occurrence and size of unmanaged waste sites.
The analysis includes:

- **Screening models:** Individual covariate models that estimate associations with waste site occurrence and site size, including uncertainty estimates and model diagnostics.
- **Joint models:** Marked LGCP models incorporating multiple urban predictors simultaneously, accounting for residual spatial variation.
- **Spatial predictions:** Estimation and visualisation of spatial intensity, uncertainty, and residual spatial effects.
- **Model evaluation:** Generation of coefficient tables, diagnostic summaries, and figures describing model results.

The script uses gridded urban covariates, waste site locations and areas, and city boundary shapefiles. Model outputs include estimated covariate effects, spatial parameters, fitted model objects, and prediction maps.

### 2. `Exposure_surface_spatial_analysis.ipynb`

**Language:** Python  
**Environment:** Google Colab / Jupyter Notebook

This notebook contains the spatial analysis of continuous unmanaged waste burden and its relationships with local urban characteristics.
The analysis includes:

- **Spatial data preparation:** Loading gridded urban covariates and waste site geometries.
- **Neighbourhood delineation:** Spatial clustering and identification of neighbourhoods and diagnostic regions based on geographical structure and waste burden.
- **Local modelling:** Random Forest regression to examine associations between urban predictors and continuous waste burden.
- **Model evaluation:** Assessment of predictive performance, predictor importance, and spatial patterns in model residuals.
- **Spatial visualisation:** Generation of maps and diagnostic figures illustrating the distribution of waste burden and its relationships with urban conditions.

The notebook contains separate analytical sections for individual cities, with configurations and predictor selections adapted to their respective datasets.

## Input data

The scripts use datasets available in the repository's `Data/` directory.

| Input | Description |
|---|---|
| Waste site locations | CSV files containing site coordinates and mapped area |
| Waste site polygons | Shapefiles representing mapped unmanaged waste footprints |
| Gridded covariates | City specific datasets containing urban predictors and continuous waste burden values |
| City boundaries | Spatial boundaries used to define the modelling domain for LGCP analyses |

The gridded datasets contain observations at approximately 30 m spatial resolution. The relevant variable names and coordinate reference systems should be verified before running the scripts.

## Software and dependencies

The analyses were developed using the following environments and principal libraries.

**R / RStudio**

- `INLA`, `inlabru`: Bayesian spatial modelling and LGCP estimation
- `sf`: Spatial data processing
- `dplyr`: Data manipulation
- `ggplot2`, `viridis`, `corrplot`: Statistical and spatial visualisation
- Additional packages are imported within individual code sections.

**Python / Google Colab**

- `numpy`, `pandas`, `geopandas`: Data manipulation and spatial processing
- `shapely`, `pyproj`: Geometric operations and coordinate transformations
- `scikit-learn`: Spatial clustering, Random Forest modelling, and model evaluation
- `libpysal`, `esda`: Spatial weights and spatial autocorrelation analysis
- `matplotlib`, `folium`: Statistical and geographical visualisation
- Additional dependencies are imported or installed within the notebook.

Users should ensure that the required libraries are installed and compatible with their local environment.

## Running the code and user modifications

**The scripts are provided in their original analytical structure and may require minor modifications before execution.** In particular, file paths currently reference the local directories and Google Drive locations used during the study.

Users should review the configuration sections of the relevant scripts and update the following where necessary:

1. **Input file paths:** Update paths to the corresponding datasets in the repository or local working directory.
2. **Output directories:** Specify where model results, figures, and intermediate files should be saved.
3. **City selection:** Run the relevant city section or update the city configuration to match the intended study area.
4. **Coordinate reference systems:** Ensure that the appropriate projected CRS is specified for spatial operations involving distances and areas.
5. **Predictor variables:** Confirm that the selected covariates correspond to the columns available in the input datasets.

### R Markdown execution
Open `Log-Gaussian-Cox.Rmd` in RStudio and execute the relevant city sections.
The screening and joint models can be run separately, although subsequent visualisation sections may require model objects or saved outputs from earlier analyses.
The modelling process can be computationally intensive, particularly for cities with large spatial datasets.

### Python notebook execution
Open `Exposure_surface_spatial_analysis.ipynb` in Google Colab or a compatible Jupyter environment.
If using Google Colab, mount Google Drive and update the input and output paths before running the relevant city sections. For local execution, replace Google Drive paths and adjust environment specific commands where required.
The notebook contains multiple city specific code blocks rather than a single automated pipeline. Users should execute the relevant sections in sequence, ensuring that objects generated in preceding blocks are available.

## Outputs and reproducibility
The scripts generate model estimates, spatial predictions, diagnostic statistics, and visualisations supporting the analyses presented in the manuscript.
Selected LGCP model outputs are provided in the repository's `Results/LGCP/` directory. Figures associated with the manuscript are available in `Figures/`.
The scripts are shared to facilitate reproducibility and further methodological development. Reproducing the published analyses requires the corresponding input datasets, appropriate software dependencies, and consistency with the model configurations used in the study.
For further methodological details, refer to the associated publication.

