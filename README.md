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
The purpose of this analysis was to determine if there were in trends between the mortality rates (per 1000 adults) between 2019 to 2021 for the 5 countries with the highest life expectancy, and the 5 countries with the lowest life expectancy. 

You can find the analysis in the Jupyter Notebook file: mortality_API_immunizationstats.ipynb

We utilized the mortality_rate_male.csv and mortality_rate_female.csv Data Frame taken from the World Development Indicator (WDI) and the life_df.csv that was created during the Immunization Rates Analysis comparing the Life expectancy of total population, Average Immunization,	Medical doctors (number) of 150 countries. We merged these 3 data frames together and further filtered them to analyze the 5 countries with the highest life expectancy, and the 5 countries with the lowest life expectancy. 


Overall we plotted numerous bar charts comparing the mortality rates in different aspects (male versus female, high life expectancy bar chart only, low life expectanch bar chart only). However, our final analysis that we presented looked at the 10 countries as a whole, taking the average of male and female mortality rates between 2019-2021 and plotting it on a bar chart. This bar chart can be found on output 15. 

4. Immunization Rates
The purpose of this analysis was to analyze the average immunization rates of 150 countries, and determine if there were any correlations between average immunization rates and medical doctor prevalence, and average immunization rates and life expectancy. 

You can find the analysis in the Jupyter Notebook file: immunization.ipynb

The Dataframe was taken from the data cleaning analysis.ipynb jupyter notebook, named: totalavgfilter.csv. 

We utilized matplotlib.pyplot, pandas, numpy, and scipy.stats for this analysis. 

These were used to plot 2 scatter plot linear regression models, including the Pearson Correlation Coefficient and the R-squared values. 

We only presented the linear regression model of the average immunization rate compared to life expectancy, as there appeared to be a moderate positive correlation of 0.58 between the two variables. 

The linear regression model for average immunization rate compared to medical doctors (output 18) had a very weak Pearson coefficient correlation of 0.11, with the scatter plot showing a number of outliers. A box plot was also used to confirm that there were outliers in the data. For the purpose of time, we suggested that it would be interesting to do further research on filtering out the outliers to assess if the correlation between average immunization rates and medical doctors would change. 


5. Immunization Rates Statistics: 
The purpose of this analysis was to analyze the average immunization rates of the 5 countries with the highest life expectancy, and the 5 countries with the lowest life expectancy that were utilized in the earlier analysis of mortality rates. We wanted to apply statistical tests to further determine if there is a relationship between life expectancy and average immunization rates. 

You can find the analysis in the Jupyter Notebook file: mortality_API_immunizationstats.ipynb (starting at output 25).

We utilized matplotlib.pyplot, pandas, and scipy.stats for this analysis. 

We had taken the data from our initial analysis of mortality rates, life expectancy, and average immunizations in the outline_df create earlier in the jupyter notebook file. We filtered out the data to only include columns for Country and Average Immunization, and added a column to split the countries into 2 groups (5 countries with the highest life expectancy, 5 countries with the lowest life expectancy). Utilizing this new column, we plotted a histogram, and box plot to obtain a better visualization of the data. We then completed a scripy.stats Independent T Test between the two groups to determine the statistical significance. 

The results were as followed: Ttest_indResult(statistic=2.939390069769216, pvalue=0.03782786257640668)

6. Hospital Counts using GeoAplify API:

The purpose of this analysis was to utilized GeoAplify API, and GeoMapping to get a better picture of the 5 countries with the highest life expectancy rates and the 5 countries with the lowest life expectancy rates. And determine if there were any relationship between the amount of hospitals within a 500 km radius of the capital city of the country and the country's life expectancy. 

You can find the analysis in the Jupyter Notebook file: mortality_API_immunizationstats.ipynb (starting at output 18).

We utilized a dataset that included the latitude and longitude coordinates of each country (world_df), which was found on Google Developer's Website. 

We utilized json, pandas, and hvplot.pandas, API for this analysis. 

Utilizing the GeoAplify API, we iterated through all the countries to determine how many hospitals were present within a 500 km radius of the Capital City with a limit of 150 counts, creating a new column and data frame called hospital_df which included the hospital count for each country. Some limitations were that 3 countries (Sweden, Nigeria, and Chad) did not have any information on the hospital count. 

We merged this dataframe that included the latitude, longitude, and hosptial count with our outline_df, which was created earlier in this jupyter notebook. We filtered the data to include Life expectancy total population,	Average Immunization,	Medical doctors (number), and Country Name for the purpose of plotting it on a map.

We then plotted all the data onto a map using hvplot.pandas. 






