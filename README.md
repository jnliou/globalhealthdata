# Analysis of Overall Healthcare Worldwide

## Overview
Our research project aims to conduct a comprehensive analysis of global health data to identify areas in greatest need of assistance or aid from organizations like the World Health Organization (WHO). Additionally, we seek to identify countries that demonstrate exemplary health outcomes and practices, serving as valuable lessons for global health improvement efforts. By analyzing various datasets and employing statistical methods, we will investigate key factors such as medical personnel prevalence, immunization rates, GDP per capita, urbanization trends, and mortality rates. Through this research, we aim to contribute to the understanding of global health disparities and provide insights to support evidence-based decision-making in healthcare planning and resource allocation.

Based on comprehensive analysis of general health data, which areas of the world are in greatest need of assistance or aid from the World Health Organization (WHO) and other organizations, and which countries demonstrate exemplary health outcomes and practices that can serve as valuable lessons for global health improvement efforts?

## Instructions

### Data sets

Data sets were obtained from the following websites:
Kaggle
World Health Organization (WHO)
World Development Indicator (WDI)
Google Developers 
THe data sets included the following information:
- Mortality Rates, Average Immunization Rates, GDP, Life Expectancy, Urban vs. Rural Population %, Medical Doctor Numbers, Latitude/Longitude 

### Data cleaning
Data cleaning can primarily be found in Jupyter's notebook "analysis.ipynb" 

Data cleaning process included the following steps:
- Years: 2015 to 2019.
- Countries that did not have Life Expectancy and Immunization Rates for all analyzed years were excluded from the analysis:
Curacao,
Greenland,
Sint Maarten (Dutch part).
- Countries that did not have Male/Female ratio  to calculate Life Expectancy for the entire population were assigned 50%:
Czech Republic,
Turkey.
- Life Expectancy for the entire population was calculated as weighted average between Male Life Expectancy and Female Life Expectancy. 
- 95 countries (63.33%) did not have complete ‘Year’ information the data was averaged out by years.
- Data frame that contains information by country with averaged information across the analyzed years has 246 countries.
- For the number of Medical Doctors, 60.98% of the countries were filtered out from the original data set because of the missing values, bringing dataset to the size of 150 countries.
- We took the average of the HepB3, DPT, and Measles Vaccine to analyze the overall immunization rates.

### Questions analyzed 

1. GDP and Medical Doctors.
- What is the purpose/driving factors to perform the analysis.
- Where a jupyter notebook with this code is.
- What dataframes were used for the anaysis.
- What statistical tools/libraries, other means were used to perform the analysis.
- Mention specific values from the results of the statistical tests that were performed.


2. Life Expectancy vs. Urban/Rural Population ratio.


3. Mortality Rates.


4. Immunization Rates.


5. Hospital Counts using GeoAplify API.



