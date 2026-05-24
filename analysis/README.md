
# Data Analysis

This folder contains scripts for performing data analysis on the cleaned and processed Eugene and Springfield CAD data.

## Purpose

The goal of this stage is to:
- Perform initial analysis on cleaned data and visualize change in response times over time.
- Perform a parallel trends analysis on the pre-shutdown data to determine if the data is valid and useable for a Difference in Differences study through a regression and visualization of those results.
- Perform a Difference in Differences study on response times by priority group, comparing them before and after CAHOOTS shutdown by using Springfield as a control variable.
- Visualize and generate results from the Difference in Differences study to determine if there is a causal effect between the shutdown and response times and answer the main research questions.

## Folder Contents

`analysis.Rmd`: 
- Groups priority levels into groups, defines a treatment and control group, creates new variables, and filters the data for pre-shutdown
- Plots average response times on a line plot to compare cities over time
- Visualizes parallel trends, runs a regression on these trends, and outputs results that determine if DiD can occur
- Performs a difference-in-differences analysis on each priority group for the Eugene CAD data by controlling for Springfield, estimating the model, determining causal effect, controlling for other variables, and plotting the results.

- Output: `results_dd.csv`, `results_pt.csv`, `plot_overall.png`, `plot_pt.png`, `plot_12.png`, `plot_34.png`, `plot_5.png`, `coefficients.png`

## Input Files

- `cleaned_eug_spd.csv`: Cleaned and merged EPD and SPD call data containing variables: `yr`, `inci_id`, `agency`, `calltime`, `priority`, `callsource`, `mins_to_arrv`, `post_shutdown`, `priority_group`

## Output Files:

- `results_pt.csv` - Dataframe of test statistics from the parallel trends analysis
- `results_dd.csv` - Dataframe of test statistics from the difference-in-differences analysis
- `plot_overall.png` - Image of the plot of average response times over time
- `plot_pt.png` - Image of the plot of the pre-shutdown trends for each priority group 
- `plot_12.png` - Image of the plot of average response times over time for the 'emergency' priority group (1-2)
- `plot_34.png` - Image of the plot of average response times over time for the 'investigative' priority group (3-4)
- `plot_5.png` - Image of the plot of average response times over time for the 'service' priority group (5)


> Note: Because of GitHUB file size limits, the cleaned data and results files are not included in this repository. To produce the cleaned dataset and results, respectively:
- See README.md in the data cleaning folder
- See "How to Run" section below

## How to Run
Make sure you have met the requirements in the "Requirements" section of the main `README.md` file, have obtained the cleaned and combined dataset of Eugene and Springfield calls from the `data cleaning` section of this repository, and the `cleaned_eug_spd.csv` file is in your root directory with the .Rmd files.

1. Run all chunks in the Rmd file `analysis.Rmd`.
- Make sure packages get imported first, and the chunks are run in order to prevent errors and messing up the data.

## Dependencies

This section uses the following R packages:

- tidyverse
- stats
- ggplot2
- fixest
- broom
