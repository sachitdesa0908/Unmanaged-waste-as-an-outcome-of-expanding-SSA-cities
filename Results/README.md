# LGCP Results

## Overview
This directory contains the outputs of the Log Gaussian Cox Process (LGCP) models developed for the study **"Unmanaged waste as an outcome of expanding sub-Saharan African cities"**, published in *npj Urban Sustainability*.
The results are organised into separate folders for the ten study cities: Abidjan, Accra, Dakar, Freetown, Johannesburg, Kampala, Kinshasa, Lagos, Maputo, and Nairobi.
The LGCP models examine associations between urban characteristics and the spatial occurrence and size of unmanaged waste sites, while accounting for underlying spatial variation.

## Directory structure
Each city folder contains the following model outputs:

| File | Description |
|---|---|
| `occurrence_effects.csv` | Estimated regression coefficients for waste site occurrence, including standard errors, lower and upper confidence interval bounds, and significance indicators for individual predictors. |
| `spatial_parameters.csv` | Estimated spatial model parameters, including spatial range, standard deviation of the latent spatial field, and mark precision, with associated uncertainty intervals. |
| `integration_points.rds` | R data object containing spatial integration points used in the LGCP modelling procedure. |
| `prediction_objects.rds` | Saved R objects associated with model predictions, supporting subsequent spatial analysis and visualisation. |
| `scaling_parameters.rds` | Saved parameters used to standardise or transform predictor variables for model fitting and interpretation. |

## Using the results
The CSV files can be accessed using standard data analysis software, including R and Python. The `.rds` files contain serialised R objects and can be loaded using `readRDS()`.
The results can be used to examine estimated predictor effects, evaluate spatial model characteristics, and reproduce selected statistical summaries and visualisations presented in the manuscript.
Users should note that predictor coefficients and spatial parameters are model dependent and should be interpreted in conjunction with the corresponding model specifications and variable transformations.

## Related code and data
The LGCP modelling procedure is implemented in `Code/Log-Gaussian-Cox.Rmd`. The corresponding waste site locations, areas, and gridded urban covariates are available in the `Data/` directory.
For further details on model specification, estimation, and interpretation, refer to the Methods and Supplementary Information of the associated publication.

