# Analysis of Overall Healthcare Worldwide

![Project Logo](https://www.e-ir.info/wp-content/uploads/fly-images/84328/Screenshot-2020-05-22-at-19.22.11-807x455-c.jpg)


## Overview

Our research project aims to conduct a comprehensive analysis of global health data to identify areas in greatest need of assistance or aid from organizations like the World Health Organization (WHO). Additionally, we seek to identify countries that demonstrate exemplary health outcomes and practices, serving as valuable lessons for global health improvement efforts. By analyzing various datasets and employing statistical methods, we will investigate key factors such as medical personnel prevalence, immunization rates, GDP per capita, urbanization trends, and mortality rates. Through this research, we aim to contribute to the understanding of global health disparities and provide insights to support evidence-based decision-making in healthcare planning and resource allocation.

**Research Question**: Based on comprehensive analysis of general health data, which areas of the world are in greatest need of assistance or aid from the World Health Organization (WHO) and other organizations, and which countries demonstrate exemplary health outcomes and practices that can serve as valuable lessons for global health improvement efforts?

The slide deck of our presentation can be found as a PDF, titled: [Presentation - Analysis of Overall Healthcare Worldwide.PDF](https://docs.google.com/presentation/d/1ocTOHkDrqGDJFO85Cjwz38St5kXDhVix88cvsFs2HfM/edit#slide=id.g252acccf8a5_0_18).

## Instructions

### Data Sets

Data sets were obtained from the following websites:
- Kaggle
- World Health Organization (WHO)
- World Development Indicator (WDI)
- Google Developers

The data sets included the following information:
- Mortality Rates
- Average Immunization Rates
- GDP
- Life Expectancy
- Urban vs. Rural Population %
- Medical Doctor Numbers
- Latitude/Longitude

### Data Cleaning

Data cleaning can primarily be found in Jupyter's notebook "analysis.ipynb". The data cleaning process included the following steps:
- Years: 2015 to 2019.
- Covid-19 Analysis of Mortality Rates looked at data from 2019 to 2021.
- Countries that did not have Life Expectancy and Immunization Rates for all analyzed years were excluded from the analysis.
- Countries that did not have Male/Female ratio to calculate Life Expectancy for the entire population were assigned 50%.
- Life Expectancy for the entire population was calculated as a weighted average between Male Life Expectancy and Female Life Expectancy.
- Data frame that contains information by country with averaged information across the analyzed years has 246 countries.
- For the number of Medical Doctors, 60.98% of the countries were filtered out from the original data set because of missing values, bringing the dataset to the size of 150 countries.
- The average of the HepB3, DPT, and Measles Vaccine was used to analyze overall immunization rates.

### Analysis

#### GDP and Medical Doctors

The purpose of this analysis is to find out the correlation between GDP per Capita and medical resources per capita, and correlation between GDP per capita and life expectancy. Then find the difference between the top 20 and bottom 20 nations. This analysis will help to understand why countries with higher GDP have higher life expectancy.

- The code for this analysis is in "GDP_vs_life_expectancy.ipynb".
- The dataframes used in this analysis are "totalavgfilter.csv" and "world-population-by-countries-dataset.csv".
- The Pearson correlation test was performed for understanding the correlativeness between two datasets. After normalizing the dataset, a log transformation was performed for a more favored result.
- By comparing the GDP per capita and life expectancy column, it returns a correlation coefficient of 0.83, indicating an optimum positive relation between GDP and life expectancy.
- The correlation test between the GDP per capita and medical doctors per capita returns a correlation coefficient of 0.72, demonstrating a strong relation between the two features.

#### Life Expectancy vs. Urban/Rural Population Ratio

The purpose of the analysis is to see if countries with different Urban/Rural population ratios have different life expectancy.

- The analysis can be found in Jupyter Notebook file: `life_expect_vs_urban_pop.ipynb`.
- Linear regression analysis, correlation analysis, and independent sample t-tests were used to check statistical significance.
- Visualizations include scatter plots, regression lines, box plots, and map visualizations.

#### Immunization Rates

The purpose of this analysis was to analyze the average immunization rates of 150 countries and determine if there were any correlations between average immunization rates and medical doctor prevalence, and average immunization rates and life expectancy.

- You can find the analysis in the Jupyter Notebook file: `immunization.ipynb`.
- We utilized matplotlib.pyplot, pandas, numpy, and scipy.stats for this analysis.
- Visualizations include scatter plots, linear regression models, Pearson Correlation Coefficients, and R-squared values.

#### Mortality Rates

The purpose of this analysis was to determine if there were trends between the mortality rates (per 1000 adults) between 2019 to 2021 for the 5 countries with the highest life expectancy and the 5 countries with the lowest life expectancy.

- You can find the analysis in the Jupyter Notebook file: `mortality_API_immunizationstats.ipynb`.
- Data from the World Development Indicator (WDI) and other sources were used for this analysis.
- Visualizations include bar charts comparing mortality rates among different groups.

#### Immunization Rates Statistics

The purpose of this analysis was to analyze the average immunization rates of the 5 countries with the highest life expectancy and the 5 countries with the lowest life expectancy. Statistical tests were applied to further determine if there is a relationship between life expectancy and average immunization rates.

- You can find the analysis in the Jupyter Notebook file: `mortality_API_immunizationstats.ipynb` (starting at output 25).
- Statistical tests include histograms, box plots, and Independent T-Tests.

### Hospital Counts using GeoAplify API

The purpose of this analysis was to utilize GeoAplify API and GeoMapping to get a better picture of the 5 countries with the highest life expectancy rates and the 5 countries with the lowest life expectancy rates. It aimed to determine if there were any relationships between the number of hospitals within a 500 km radius of the capital city of the country and the country's life expectancy.

- You can find the analysis in the Jupyter Notebook file: `mortality_API_immunizationstats.ipynb` (starting at output 24).
- GeoAplify API, json, pandas, and hvplot.pandas were used for this analysis.

**Note**: You need to save your "geoapify_key" into the `config.py` file to run the code sufficiently.

### References

The datasets were taken from the following sources:
- [World Bank](https://data.worldbank.org/indicator/SP.DYN.AMRT.FE)
- [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/latitude-and-longitude-for-every-country-and-state)
- [World Population Dataset](https://www.kaggle.com/datasets/kiranshahi/life-expectancy-dataset?datasetId=1980580&sortBy=dateRun&tab=profile)

---

This revised README provides a more organized and structured overview of
