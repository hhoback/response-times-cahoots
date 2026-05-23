
# Data Cleaning

This folder contains scripts for cleaning the raw Eugene CAD data and Springfield SPD data in preparation for data analysis.

## Purpose

The goal of this stage is to:
- Stack each year of data per city 
- Clean and standardize raw call data
- Calculate response times and combine datasets into a single dataset for easy analysis
- Filter out unusable, bad, or missing data
- Convert clean data into a .csv file for use in analyis

## Folder Contents

- `clean_data.Rmd`: Loads raw data, fixes formatting issues, removes null values, combines data, creates new variables, and outputs a cleaned version ready for analysis.

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

- `cleaned_eug_spd.csv`: Cleaned and merged EPD and SPD call data containing variables: `year`, `agency`, `inci_id`, `calltime`, `callsoure`, `priority`, `nature`, `primeunit`, and `mins_to_arrv`. 

## How to Run

> Note: Because of GitHUB file size limits, the raw data and resulting cleaned dataset are not included in this repository. To produce the cleaned dataset:
1. Ensure all raw data files are in a `data` folder. Refer to the `File Structure` section of the main `README.md` file to ensure proper structure.
2.  Run all chunks in the Rmd file `clean_data.Rmd` in order.
- Make sure packages get imported first, and the chunks are run in order to prevent errors and messing up the data.

## Dependencies

This section uses the following R packages:

- readxl
- tidyverse
- lubridate
- janitor
