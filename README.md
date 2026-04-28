
# Data Cleaning

This folder contains scripts for cleaning the raw Eugene CAD data and Springfield SPD data in preparation for data analysis.

## Purpose

The goal of this stage is to:
- Stack each year of data per city 
- Clean and standardize raw call data
- Combine datasets into a single dataset for easy analysis
- Create new variables for classifying calls

## Folder Contents

- `data_prep_clean.Rmd`: Loads raw data, fixes formatting issues, removes null values, combines data, creates new variables, and outputs a cleaned version ready for analysis. 

## Input Files

- `2015-2025 SPD Calls for Service.xlsx`
- `EugeneCAD2015noloc.csv`
- `EugeneCAD2016noloc.csv`
- `EugeneCAD2017noloc.csv`
- `EugeneCAD2018noloc.csv`
- `EugeneCAD2019noloc.csv`
- `EugeneCAD2020noloc.csv`
- `EugeneCAD2021noloc.csv`
- `EugeneCAD2022noloc.csv`
- `EugeneCAD2023noloc.csv`
- `EugeneCAD2024noloc.csv`
- `EugeneCAD2025noloc.csv`

## Output Files

- `epd_spd_cleaned.csv`: Cleaned and merged EPD and SPD call data containing variables: `yr`, `inci_id`, `agency`, `calltime`, `priority`, `callsource`, `mins_to_arrv`, `post_shutdown`, `priority_group`

## How to Run

Run all chunks in the Rmd file `data_prep_clean.Rmd`.
- Make sure packages get imported first, and the chunks are run in order to prevent errors and messing up the data.

## Dependencies

This project uses the following R packages:

- dplyr
- tidyr
- ggplot2
- base
