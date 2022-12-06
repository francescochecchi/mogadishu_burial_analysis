# Burial patterns during the first COVID-19 epidemic wave in Mogadishu, Somalia: Analysis of satellite imagery
Warsame et al. (2021) https://www.ijidonline.com/article/S1201-9712(21)00758-X/fulltext

# Notes on data and R analysis code
30 March 2021  
Francesco Checchi  
Department of Infectious Disease Epidemiology  
Faculty of Epidemiology and Population Health, Keppel St  
London School of Hygiene and Tropical Medicine  
Francesco.checchi@lshtm.ac.uk  

## Background on the study
This repository contains data and R scripts required to replicate an analysis of very high-resolution satellite images covering Banadir Region (the administrative level 1 unit encompassing the capital, Mogadishu), Somalia during a period between 2016 and September 2020. The analysis was conducted by the Somali Disaster Resilience Institute (http://sdri.so/), The Satellite Applications Catapult (https://sa.catapult.org.uk/) and the London School of Hygiene and Tropical Medicine (www.lshtm.ac.uk). We sought to quantify the rate of burials over time in all cemeteries we were able to identify and source imagery for across Mogadishu. We compared pre-2020 to 2020 trends to estimate the rate of excess burials associated with the pandemic. We also scaled the curve of excess burials to varying assumed levels of crude death rate, and combined this with displacement-adjusted estimates of population size over time to quantify the number of excess deaths over Jan-Sep 2020 in Banadir Region.

## Datasets
All datasets required to replicate the analysis are included in the file <banadir_covid_burial_data.xlsx>. The file includes a ‘dictionary’ tab, whose column ‘use’ determines which variables are read into R analysis (below). Only variables marked as ‘yes’ for this column are necessary to replicate the analysis.

## R code scripts
The script `banadir_covid_control_code.R` loads necessary R packages, sets parameters (these can be modified by the user), loads datasets, calls dependent scripts (below) and outputs some tables and figures. Only this script needs to be run to replicate the analysis. Computation time should be <10 min on a standard laptop.

The dependent script files, called from the above script, are, in order of implementation:
* `banadir_covid_bespoke_functions.R`: this script contains all the user-defined functions (not all are in fact used);
* `banadir_covid_prepare_data.R`: this script prepares data for analysis;
* `banadir_covid_impute_graves.R`: this script fits a general additive model to impute graves from cemetery surface area, and outputs descriptive tables and figures;
* `banadir_covid_excess_burials.R`: this script implements the main analysis and outputs tables and figures.

## Requirements to replicate the analysis
Datasets and R code files must be stored on the same folder, where output files will be saved. The directory for reading files is set automatically while the control code is run.
It is recommended to run the code from the open-source RStudio interface (https://rstudio.com/ ).
