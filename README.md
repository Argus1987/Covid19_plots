# Covid19_plots


# Overview
The notebook AnalyzeCovid19.ipynb contains a simple processing pipeline for analyzing some Covid19 data. It will first download data from John Hopkins (JH) in the form of csv files for the (1) confirmed cases, (2) deaths, and (3) recovered cases.  The first few parts of this workflow follow a great tutorial published by [B. Chen](https://towardsdatascience.com/covid-19-data-processing-58aaa3663f6) who discusses a step-by-step procedure on using Pandas to prepare a dataset for analysis in Python. After implementing this, I developed my own plotting routines to create a few custom visualations for some countries that I have personal interest in tracking during this pandemic. These countries are US, UK, China, and Italy.


# Sample Output Plots
Here are a few sample plots that this pipeline will produce including a bar graph with the top-20 death totals by country, line plots of the 7-day moving average of new cases, and a scatterplot of new cases vs. new deaths

![top-20 deaths by country](/screenshot_deaths-by-country.png)
![7-day moving average new cases](/screenshot_new-daily-cases.png)
![new cases vs. new deaths](/screenshot_new-cases-vs-new-deaths.png)


#### To run this notebook, please change the global destination folder as needed for your computer just below the list of imported libraries.

## Workflow
This is a brief discription of the functions that I developed that make up this workflow.

### download_data
This function contains the URLs for the JH data as well as path for downloading on local on your computer. This function will check for any previous data files that may have previously been downloaded and delete them before downloading the latest from JH.

### load_data
This is simple function that loads the csv files via Pandas.

### clean_data
This function does all of the reshaping, merging, grouping, sorting, etc. It ultimately produces a cleaned data set that is passed to the various plotting functions.

### barplot_deaths
This is a barplot showing deaths by country sorted in descending order for the top 20.

### lineplots_newcases
This function makes line plots showing the 7-day moving average of new cases. I created 2 versions of this plot. One normalizes for each country's population and the other does not.  I was curious to see how misleading the raw data would be if not accounting for population.

### scatterplots
This function makes a scatterplot showing the relationship between new cases and new deaths.