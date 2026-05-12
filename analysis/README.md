
# Data Analyis

This folder contains scripts for performing data analysis on the cleaned and processed Eugene and Springfield CAD data.

## Purpose

The goal of this stage is to:
- Perform initial analysis on cleaned data and visualize change in response times over time
- Perform a parallel trends analysis on the pre-shutdown data to determine if the data is valid and useable for a Difference in Differences study through a regression and visualization of those results
- Perform a Difference in Differences study on response times by priority group, comparing them before and after CAHOOTS shutdown by using Springfield as a control variable.
- Visualize and generate results from the Difference in Differences study to determine if there is a causal effect between the shutdown and response times and answer the main research questions

## Folder Contents

`initial_analysis.Rmd`: 
- Groups variables, calculates average response time, and plots those times on a line plot to compare cities over time
- Output: Line plots, interpretation of results

`parallel_trends.Rmd`:
- Groups priority levels into groups, defines a treatment and control group, and filters the data for pre-shutdown
- Groups observations by year, treatment, and priority group, and calculates average response time over time by treatment group per priority group
- Visualizes parallel trends, runs a regression on these trends, and outputs results that determine if DiD can occur
- Output: `results_pt.csv`, line plots, interpretation of results

`diff_in_diff.Rmd`:
- Performs the main data analysis through a difference in differences study by definining a shutdown period, estimating the model, determining causal effect, controlling for other variables, and plotting the results through a coefficient plot.
- Output: `results_did.csv`, coefficient plot, interpretation of results

## Input Files

- `cleaned_eug_spd.csv`: Cleaned and merged EPD and SPD call data containing variables: `yr`, `inci_id`, `agency`, `calltime`, `priority`, `callsource`, `mins_to_arrv`, `post_shutdown`, `priority_group`

## Output Files:

- `results_dd.csv`: DataFrame containing test statistics and p-values from difference-in-differences analysis
- `results_pt.csv`: DataFrame containing test statistics and p-values from parallel trends analysis
- Line plots, coefficient plots, and all visualizations of results


> Note: Because of GitHUB file size limits, the cleaned data and results files are not included in this repository. To produce the cleaned dataset and results, respectively:
- See README.md in the data cleaning folder
- See "How to Run" section below

## How to Run
Make sure you have met the requirements in the "Requirements" section of the main `README.md` file, have obtained the cleaned and combined dataset of Eugene and Springfield calls from the `data cleaning` section of this repository, and the `cleaned_eug_spd.csv` file is in your root directory with the .Rmd files.

1. Run all chunks in the Rmd file `initial_analysis.Rmd`.
2. Run all chunks in the Rmd file `parallel_trends.Rmd`.
3. Run all chunks in the Rmd file `diff_in_diff.Rmd`.
- Make sure packages get imported first, and the chunks are run in order to prevent errors and messing up the data.

## Dependencies

This section uses the following R packages:

- tidyverse
- stats
- ggplot2
