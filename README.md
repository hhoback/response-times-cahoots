# Analysis of Emergency Response Times in Eugene and Springfield

This repository contains data cleaning, processing, and statistical analysis of police department response times in Eugene and Springfield, OR from 2015 to 2025. The analysis compares response times over time between the two cities and uses Springfield as a control to see how response times changed in Eugene after CAHOOTS shutdown. These analyses are done by grouping each priority level into four groups to account for different response times among priority levels.  

The repository is organized into two main parts:
- `/data cleaning`: contains data cleaning and preparation notebooks
- `/analysis`: contains statistical analysis notebooks

For more details, see the individual README files in the cleaning and analysis folders.

## File Structure
Reference this file structure before running any notebooks to ensure everything is in the right place and runs correctly.

DSCI 410 Research Project/
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
├── cleaned_eug_spd.csv                         !- This file is re-generated when running files -!
├── clean_data.Rmd
├── initial_analysis.Rmd
├── parallel_trends.Rmd
└── diff_in_diff.Rmd
