# Data Science Solution in Improving the Occupancy of the Nursing Facilities

Chien Yuan Chang

## Abstract
The goal of this project is to deliver a well-scoped project proposal and preliminary analysis to struggling nursing facilities with low occupancy to let them understand and accept how data science can help them increase the occupancy. I used the data of [Nursing Homes Including Rehab Services - Provider Information](https://data.cms.gov/provider-data/dataset/4pq5-n9py) on [Centers for Medicare & Medicaid Services](https://www.cms.gov/) to do preliminary analysis and develop a proposal of the regression model. I used average state occupancy, the year of approved, the number of certified beds, the quality measure rating, and the health inspection rating to build a baseline model to predict the occupancy with MAE of 10% and proposed to bring in more regional data, data engineering, and the detailed scores of behind the ratings to improve the model with less than 5% MAE in the future to help nursing facilities identify and prioritize which areas to improve to increase the occupancy. 

## Design
* Backstory
    * Occupancy at U.S skilled nursing facilities has been stable between 80% and 85% for years. However, there was a huge drop to about 70% in 2020 due to the pandemic. Many facilities have been facing challenges.
* Business Problem
    * How can nursing facilities with the occupancy below the national average or the average of its state increase its occupancy?
* Solution paths:
    * Build a regression model to interpret the factors of the occupancy.
* Impact hypothesis
    * By better understanding how the factors affect the occupancy, the nursing facilities can make more informed decisions about identifying and prioritizing which areas to improve to increase their occupancy.
* Measures of success:
    * Adjust R-squared is above 0.5.
    * The nursing facilities with the occupancy below the average of its state increase the occupancy to the average of its state.
* Risks and assumptions:
    * Risk: The information of marketing effort and the population structure of the regions  is lacking.
    * Assumption: The occupancy is correlated with the quality measures.

## Data
* Dataset
    * [Nursing Homes Including Rehab Services - Provider Information](https://data.cms.gov/provider-data/dataset/4pq5-n9py)
* Data source
    * One of [21 datasets of nursing homes including rehab services](https://data.cms.gov/provider-data/topics/nursing-homes) on [CMS.gov](https://www.cms.gov/) (The Centers for Medicare & Medicaid Services)
* Data size
    * 15,265 nursing facilities with 88 columns such as basic information and categorical features of the nursing facility, five-star ratings of seven major measures, detailed scores for calculating some of the ratings, and the information of the penalty and fine
* Target
    * Occupany 
* Features of the baseline model
    * Average state occupancy, the year of approved, the number of certified beds, the quality measure rating, and the health inspection rating

## Algorithms

*Occupancy*

* **Average Number of Residents per Day** divided by **Number of Certified Beds** to get the **Occupancy** as the target in the regression model
* Outliers of occupancy which fell outside +/- three standard deviations were removed
* **Average State Occupancy** was calculated by each state as a feature
* **The difference between each nursing facility and its state average occupancy** was calculated as the target for EDA to control the huge regional effect

*Mapping*

* The data of **Latitude** and **Longitude** for mapping on Tableau Public was converted from the addresses of the nursing facilities by online geocoding tool [Census Geocoder](https://geocoding.geo.census.gov/) and [Geoapify](https://www.geoapify.com/tools/geocoding-online)

*Other Data Cleaning and Engineering*

* The data without all seven ratings were removed
* Two nursing facilities which were approved just in 2020 were removed
* Excel `YEAR()` was used to get the **Approved Year** from **Date First Approved to Provide Medicare and Medicaid Services**
* **Total Amount of Fines in Dollars** divided by **Number of Certified Beds** to get **Fine Per Bed** as a new column
* **COVID-19 Vaccination Rate** for the residents and healthcare personnels were added by Excel `VLOOKUP()` from [COVID-19 Vaccination Rates - Provider Data](https://data.cms.gov/provider-data/dataset/pvax-cv19)
* The final data for EDA and baseline model contained 11,651 datapoints 

*Baseline Model*
  
The entire training dataset of 11,651 records was split into 80/20 train vs. holdout. Simple Linear Regression was used for baseline model, and the MAE was 0.105 and Adjusted R-square was 0.167.

Features|Coefficient|P-Value|
---:|---:|---:|
Constant|-1.3314|<0.001|
Average State Occupancy|1.0586|<0.001|
Quality Measure Rating|0.0100|<0.001|
Health Inspection Rating|0.0021|0.066|
Approved Year|0.0006|<0.001|
Number of Certified Beds|-0.0002|<0.001|

*Future Work*

* Goal
    * MAE < 0.05
* New data/features
    * Regional census data
        * Population structure
        * Density
        * Economics
    * 15 different physical and clinical measures of quality measure 
    * 3 most recent health inspections
        * Survey date
        * Health scores
* Feature engineering
* Feature selection
* Try Lasso and Ridge
* Cross-validation

## Tools
* Microsoft Excel for data cleaning and analysis
* Tableau Public for mapping and data visualization
* Google Slides for data visualizations and presentation
* Python Pandas, Statsmodels and Scikit-learn for baseline regression model

## Communication
In addition to the slides of the [final presentation](final_presentation.pdf), [charts](images/), [Excel sheet](data/), [Tableau Public vizzes](https://public.tableau.com/app/profile/koscew/viz/NursingFacilitiesinU_S_CMSdata/Map) and this written description, the findings will be posted on [my personal blog](https://koscew.github.io/) in the future.
