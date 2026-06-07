# Analysis of Emergency Response Times in Eugene and Springfield

This repository contains data cleaning, processing, and statistical analysis of police department response times in Eugene and Springfield, OR from 2015 to 2025. The analysis compares response times over time between the two cities and uses Springfield as a control to see how response times changed in Eugene after CAHOOTS shutdown. These analyses are done by grouping priority levels together to account for different response times among calls with different priorities.  

The repository is organized into two main parts:
- `/data cleaning`: contains data cleaning and preparation notebooks
- `/analysis`: contains statistical analysis notebooks and results

For more details, see the individual README files in the cleaning and analysis folders.

## Requirements
All components of this project use R and the notebooks were created using RStudio. Make sure you have a program installed on your computer that can run R with the most recent version.

## File Structure
Reference this file structure before running any notebooks to ensure everything is in the right place and runs correctly.
```
DSCI 410 Research Project/
├── analysis.Rmd
├── cleaned_eug_spd.csv                     !- This file is re-generated when running files -!
├── clean_data.Rmd
└── data/
│   ├── 2015-2025 SPD Calls for Service.xlsx
│   ├── 2015-2025 SPD Responding Units.xlsx
│   ├── EugeneCAD2015noloc.csv
│   ├── EugeneCAD2016noloc.csv
│   ├── EugeneCAD2017noloc.csv
│   ├── EugeneCAD2018noloc.csv
│   ├── EugeneCAD2019noloc.csv
│   ├── EugeneCAD2020noloc.csv
│   ├── EugeneCAD2021noloc.csv
│   ├── EugeneCAD2022noloc.csv
│   ├── EugeneCAD2023noloc.csv
│   ├── EugeneCAD2024noloc.csv
│   └── EugeneCAD2025noloc.csv
└── figures/                                !- This folder is created after running files -!
│   ├── freq_pg.png                         !- This file is re-generated when running files -!
│   ├── plot_overall.png                    !- This file is re-generated when running files -!
│   ├── pt_facet.png                        !- This file is re-generated when running files -!
│   ├── response_times_12.png               !- This file is re-generated when running files -!
│   ├── response_times_34.png               !- This file is re-generated when running files -!
│   └── response_times_4.png                !- This file is re-generated when running files -!
└── results/                                !- This folder is created after running files -!
│   ├── results_did_pg.csv                  !- This file is re-generated when running files -!
│   ├── results_did.csv                     !- This file is re-generated when running files -!
│   ├── results_pt_pg.csv                   !- This file is re-generated when running files -!
│   └── results_pt.csv                      !- This file is re-generated when running files -!
```
> Note: The cleaned .csv files are intentionally located in the root directory, not in data/

## How to Run
Before running any files, ensure you have met all [Requirements] (#requirements).

### 1. Run all chunks in `clean_data.Rmd`
Cleans and prepares the raw data and produces an output file of the cleaned data, detailed in the individual `README.md` file in the `data cleaning` folder.
> Note: Each step below uses the cleaned data file produced by this step. Run `clean_data.Rmd` first.

### 2. Run all chunks in `analysis.Rmd`
Performs a full analysis of the EPD and SPD data for each priority group. Compares average response times over time between agencies, performing a parallel trends analysis on the pre-shutdown data. Performs a difference-in-differences study of the EPD and SPD data for each priority group, looking at how average response times changed in Eugene after CAHOOTS shut down, using Springfield as a control. Produces output files of the analysis, detailed in the individual `README.md` file in the `analysis/` folder. 

#
> Refer to the individual `README.md` files in the `analysis/` and `data cleaning/` folders for further information about each process.
