<<<<<<< HEAD
# Analysing ACT and SAT participation rates in California in 2019

 - [Problem Statement](#Problem-Statement) 
 - [Data Sources](#Data-Sources)
 - [Executive Summary](#Executive-Summary)
 - [Notebook Contents](#Notebook-Contents)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusion & Recommendations](#Conclusion-&-Recommendations)


## Problem Statement
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university. 

It is widely accepted that higher education increases an individual's job prospects and lowers the chance of being unemployed. We would therefore expect a negative relationship between test participation rates and unemployment rates.

In this scenario, we play the role of a non-profit social enterprise in California promoting quality jobs to raise the standard of living and to lower the unemployment rate. We want to examine the effect of test participation on unemployment rates. Do ACT or SAT test participation affect unemployment rates more, or vice versa? How different are test participation rates in different states of US and within California? What policies can we likely recommend to improve test participation?

--- 
## Data Sources
The sources of the datasets used in this analysis:
- State ACT 2017, 2018, 2019 dataset
- State SAT 2017, 2018, 2019 dataset
- California ACT and SAT 2019 dataset
- [State GDP dataset, 2019](https://www.bea.gov/data/gdp/gdp-state)
- [State unemployment dataset, 2019](https://www.bls.gov/web/laus/laumstrk.htm)
- [State population dataset, 2019](https://www.census.gov/programs-surveys/popest.html)
- [County GDP dataset 2017-2019](https://www.bea.gov/data/gdp/gdp-county-metro-and-other-areas)
- [California county stats dataset, 2019](https://www.counties.org/data-and-research)

---
## Executive Summary
**INTRODUCTION**

This project seeks to examine the participation rate of the ACT and SAT tests and its effect on unemployment rates in California counties. We will be playing the role of a non-profit social organisation in California promoting quality jobs to raise the standard of living and to lower the unemployment rate.

The cleaned datasets will be organised at the state level and California county level, and statistical data consisting of macroeconomic data is used to explore relationships between test participations and unemployment rates.

**METHODOLOGY**

To investigate on this topic, the team has performed data cleaning on the datasets, explored and analysed the data and created visualisations to understand the data and communicate the findings.

Firstly, data import and cleaning was performed with one or more of these steps
- Reading and displaying the CSV datasets
- Replacement of incorrect or null values and data types
- Removal of duplicate rows and unnecessary rows and columns
- Merging of initial datasets into two combined final datasets (at US state level and California county level) for Exploratory Data analysis and Visualisations

Secondly, exploratory data analysis was done on the final two merged datasets.
- Explored by sorting states with the highest and lowest participation rates from 2017 to 2019
- Grouped US states by census divisions to find trends in participation rates and unemployment rates
- Grouped California counties accordingly to caucuses to identify trends in participation rates and unemployment rates

Lastly, visualisation was done using the final two merged datasets to reveal further trends. Any obvious patterns or trends were interpreted and used in the recommendations. Some of the plots we use include:
- Heatmap to identify relationships and collinearity between different factors
- Histograms to visualise the shape and skewness of distributions 
- Boxplots to identify central tendency and spread in variables
- Scatterplots with regression lines to view the relationship between features
- Barplots grouped by hue to identify states and counties quickly instead of using tables.

By working in this manner, we are able to draw conclusions and find relationships between the factors and participation rate.
We are then able to provide recommendation based on the exploratory analysis and visualisation that we have performed.

**SIGNIFICANT FINDINGS**

Many findings on the SAT and ACT participation rates, as well as unemployment rates and GDP data, were gathered when analysing the datasets.

- Participation rates vs Unemployment rates in 2019: The correlation between unemployment rates and ACT or SAT participation rates is very weak at the state level. There is no strong evidence to suggest that a lower or high unemployment rate contributes to higher test participation rates. On the county level, the correlation is also quite weak and does not drastically changes.
- Participation rates trend from 2017 to 2019: In the US, ACT participation rates seem to be on the decline, while SAT participation rates have moved up.
- National participation rates of ACT and SAT: States tend to have high participation rates in one test or the other, seldom both. Between 2017 and 2019, only 2 states have above 50% participation rates for both tests in each of the three years.
- Participation rates California vs national: As a state, California has seen its ACT participation dropped from **0.31 to 0.23** while SAT participation has risen from **0.53 to 0.63** between 2017 to 2019. This is in line with the national trend. Compared to the national median, California has below average ACT and above average SAT participation rates.
- Unemployment rates California vs national: The unemployment rates ranged from **2.1% to 5.5%**, with California at the higher end of the range at **4.1%**.
- Participation rates for California counties: ACT participation rates range from **1% to 63%** while SAT participation rates range from **8% to 50%**. Gerenally, urban areas tend to have higher participaton rates in both test and favour SATs over ACTs, when compared with suburban and rural areas.

### Notebook Contents
- Background
- Data import and cleaning
- Data Dictionary
- Exploratory Data Analysis
- Data Visualization
- Conclusion and Recommendations
---

## Data Dictionary

**Data Dictionary for California dataset by county (ca_cleaned)**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**county**|*object*|ca_cleaned|Name of county in California|
|**pop**|*int64*|ca_cleaned|Population of county, 2019| 
|**gdppercap**|*float64*|ca_cleaned|GDP per capita of county (in thousands of USD), 2019| 
|**edupercap**|*float64*|ca_cleaned|Education expenditure per capita of county (in thousands of USD), 2019| 
|**unemployrate**|*float64*|ca_cleaned|Unemployment rate of county (%), 2019| 
|**pov_all_pct**|*float64*|ca_cleaned|Poverty level of all ages in county (%), 2019| 
|**pov_u18_pct**|*float64*|ca_cleaned|Poverty level of people under age 18 in county (%), 2019| 
|**household**|*float64*|ca_cleaned|Median household income in county (in USD), 2019| 
|**caucus**|*object*|ca_cleaned|Caucus classification of county - Urban, Suburban, Rural| 
|**act_part**|*float64*|ca_cleaned|ACT participation rate (%), 2019| 
|**sat_part**|*float64*|ca_cleaned|SAT participation rate (%), 2019|

**Data Dictionary for National dataset by state (state_cleaned)**
 
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|state_cleaned|Name of state in the US|
|**statecode**|*object*|state_cleaned|State code of state| 
|**gdppercap**|*float64*|state_cleaned|GDP per capita of state (in USD), 2019| 
|**pop19**|*int64*|state_cleaned|Population of state, 2019| 
|**unemployrate**|*float64*|state_cleaned|Unemployment rate of state (%), 2019| 
|**census**|*object*|state_cleaned|Census division classification of states - Pacific, Mountain, West North Central, East North Central, West South Central, East South Central, South Atlantic, Middle Atlantic, New England| 
|**act17_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2017| 
|**act18_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2018| 
|**act19_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2019| 
|**sat17_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2017| 
|**sat18_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2018|
|**sat19_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2019|

---
## Conclusion & Recommendations 
**Conclusion**

Although California has a high GDP per capita among the other states, it also has a high unemployment rate. California follows the trend of many other richer states in that it has higher participation rates in SAT than ACT test. However there is very little correlation to show that unemployment rate and test participation rate are actually related at the state level.

The correlation between test participation rates and unemployment rates at the county level in California is negative, but not very strong. After removing outliers, the correlation is **-0.38 for ACT and -0.36 for SAT**, yielding the same conclusion that one variable would be a poor predictor for the other.

There seems to be a more pronounced effect in the urban areas, where an increase in participation rate brings a greater change in the unemployment rate. Rural areas seemed to have the opposite effect.

In order to increase the participation rate of standardized tests, lowering the unemployment rate of any county is unlikely to help much. Similarly, hoping to lower the unemployment rate by encouraging students to take the tests will likely give a poor result.

**Recommendations**

There are other ways, not in the scope of this notebook, to consider.

To tackle any financial disadvantages among population:
- Increase percentage of budget allocated for education for each county 
- Provide free/subsidized preparation courses and test for low-income students to raise participation rates
- Introduce scholarship programs for students in counties with lower GDP per capita and household income to pursue higher education

To tackle any social inequality:
=======
# Analysing ACT and SAT participation rates in California in 2019

 - [Problem Statement](#Problem-Statement) 
 - [Data Sources](#Data-Sources)
 - [Executive Summary](#Executive-Summary)
 - [Notebook Contents](#Notebook-Contents)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusion & Recommendations](#Conclusion-&-Recommendations)


## Problem Statement
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university. 

It is widely accepted that higher education increases an individual's job prospects and lowers the chance of being unemployed. We would therefore expect a negative relationship between test participation rates and unemployment rates.

In this scenario, we play the role of a non-profit social enterprise in California promoting quality jobs to raise the standard of living and to lower the unemployment rate. We want to examine the effect of test participation on unemployment rates. Do ACT or SAT test participation affect unemployment rates more, or vice versa? How different are test participation rates in different states of US and within California? What policies can we likely recommend to improve test participation?

--- 
## Data Sources
The sources of the datasets used in this analysis:
- State ACT 2017, 2018, 2019 dataset
- State SAT 2017, 2018, 2019 dataset
- California ACT and SAT 2019 dataset
- [State GDP dataset, 2019](https://www.bea.gov/data/gdp/gdp-state)
- [State unemployment dataset, 2019](https://www.bls.gov/web/laus/laumstrk.htm)
- [State population dataset, 2019](https://www.census.gov/programs-surveys/popest.html)
- [County GDP dataset 2017-2019](https://www.bea.gov/data/gdp/gdp-county-metro-and-other-areas)
- [California county stats dataset, 2019](https://www.counties.org/data-and-research)

---
## Executive Summary
**INTRODUCTION**

This project seeks to examine the participation rate of the ACT and SAT tests and its effect on unemployment rates in California counties. We will be playing the role of a non-profit social organisation in California promoting quality jobs to raise the standard of living and to lower the unemployment rate.

The cleaned datasets will be organised at the state level and California county level, and statistical data consisting of macroeconomic data is used to explore relationships between test participations and unemployment rates.

**METHODOLOGY**

To investigate on this topic, the team has performed data cleaning on the datasets, explored and analysed the data and created visualisations to understand the data and communicate the findings.

Firstly, data import and cleaning was performed with one or more of these steps
- Reading and displaying the CSV datasets
- Replacement of incorrect or null values and data types
- Removal of duplicate rows and unnecessary rows and columns
- Merging of initial datasets into two combined final datasets (at US state level and California county level) for Exploratory Data analysis and Visualisations

Secondly, exploratory data analysis was done on the final two merged datasets.
- Explored by sorting states with the highest and lowest participation rates from 2017 to 2019
- Grouped US states by census divisions to find trends in participation rates and unemployment rates
- Grouped California counties accordingly to caucuses to identify trends in participation rates and unemployment rates

Lastly, visualisation was done using the final two merged datasets to reveal further trends. Any obvious patterns or trends were interpreted and used in the recommendations. Some of the plots we use include:
- Heatmap to identify relationships and collinearity between different factors
- Histograms to visualise the shape and skewness of distributions 
- Boxplots to identify central tendency and spread in variables
- Scatterplots with regression lines to view the relationship between features
- Barplots grouped by hue to identify states and counties quickly instead of using tables.

By working in this manner, we are able to draw conclusions and find relationships between the factors and participation rate.
We are then able to provide recommendation based on the exploratory analysis and visualisation that we have performed.

**SIGNIFICANT FINDINGS**

Many findings on the SAT and ACT participation rates, as well as unemployment rates and GDP data, were gathered when analysing the datasets.

- Participation rates vs Unemployment rates in 2019: The correlation between unemployment rates and ACT or SAT participation rates is very weak at the state level. There is no strong evidence to suggest that a lower or high unemployment rate contributes to higher test participation rates. On the county level, the correlation is also quite weak and does not drastically changes.
- Participation rates trend from 2017 to 2019: In the US, ACT participation rates seem to be on the decline, while SAT participation rates have moved up.
- National participation rates of ACT and SAT: States tend to have high participation rates in one test or the other, seldom both. Between 2017 and 2019, only 2 states have above 50% participation rates for both tests in each of the three years.
- Participation rates California vs national: As a state, California has seen its ACT participation dropped from **0.31 to 0.23** while SAT participation has risen from **0.53 to 0.63** between 2017 to 2019. This is in line with the national trend. Compared to the national median, California has below average ACT and above average SAT participation rates.
- Unemployment rates California vs national: The unemployment rates ranged from **2.1% to 5.5%**, with California at the higher end of the range at **4.1%**.
- Participation rates for California counties: ACT participation rates range from **1% to 63%** while SAT participation rates range from **8% to 50%**. Gerenally, urban areas tend to have higher participaton rates in both test and favour SATs over ACTs, when compared with suburban and rural areas.

### Notebook Contents
- Background
- Data import and cleaning
- Data Dictionary
- Exploratory Data Analysis
- Data Visualization
- Conclusion and Recommendations
---

## Data Dictionary

**Data Dictionary for California dataset by county (ca_cleaned)**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**county**|*object*|ca_cleaned|Name of county in California|
|**pop**|*int64*|ca_cleaned|Population of county, 2019| 
|**gdppercap**|*float64*|ca_cleaned|GDP per capita of county (in thousands of USD), 2019| 
|**edupercap**|*float64*|ca_cleaned|Education expenditure per capita of county (in thousands of USD), 2019| 
|**unemployrate**|*float64*|ca_cleaned|Unemployment rate of county (%), 2019| 
|**pov_all_pct**|*float64*|ca_cleaned|Poverty level of all ages in county (%), 2019| 
|**pov_u18_pct**|*float64*|ca_cleaned|Poverty level of people under age 18 in county (%), 2019| 
|**household**|*float64*|ca_cleaned|Median household income in county (in USD), 2019| 
|**caucus**|*object*|ca_cleaned|Caucus classification of county - Urban, Suburban, Rural| 
|**act_part**|*float64*|ca_cleaned|ACT participation rate (%), 2019| 
|**sat_part**|*float64*|ca_cleaned|SAT participation rate (%), 2019|

**Data Dictionary for National dataset by state (state_cleaned)**
 
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|state_cleaned|Name of state in the US|
|**statecode**|*object*|state_cleaned|State code of state| 
|**gdppercap**|*float64*|state_cleaned|GDP per capita of state (in USD), 2019| 
|**pop19**|*int64*|state_cleaned|Population of state, 2019| 
|**unemployrate**|*float64*|state_cleaned|Unemployment rate of state (%), 2019| 
|**census**|*object*|state_cleaned|Census division classification of states - Pacific, Mountain, West North Central, East North Central, West South Central, East South Central, South Atlantic, Middle Atlantic, New England| 
|**act17_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2017| 
|**act18_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2018| 
|**act19_part**|*float64*|state_cleaned|Statewide ACT Participation Rate, 2019| 
|**sat17_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2017| 
|**sat18_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2018|
|**sat19_part**|*float64*|state_cleaned|Statewide SAT Participation Rate, 2019|

---
## Conclusion & Recommendations 
**Conclusion**

Although California has a high GDP per capita among the other states, it also has a high unemployment rate. California follows the trend of many other richer states in that it has higher participation rates in SAT than ACT test. However there is very little correlation to show that unemployment rate and test participation rate are actually related at the state level.

The correlation between test participation rates and unemployment rates at the county level in California is negative, but not very strong. After removing outliers, the correlation is **-0.38 for ACT and -0.36 for SAT**, yielding the same conclusion that one variable would be a poor predictor for the other.

There seems to be a more pronounced effect in the urban areas, where an increase in participation rate brings a greater change in the unemployment rate. Rural areas seemed to have the opposite effect.

In order to increase the participation rate of standardized tests, lowering the unemployment rate of any county is unlikely to help much. Similarly, hoping to lower the unemployment rate by encouraging students to take the tests will likely give a poor result.

**Recommendations**

There are other ways, not in the scope of this notebook, to consider.

To tackle any financial disadvantages among population:
- Increase percentage of budget allocated for education for each county 
- Provide free/subsidized preparation courses and test for low-income students to raise participation rates
- Introduce scholarship programs for students in counties with lower GDP per capita and household income to pursue higher education

To tackle any social inequality:
>>>>>>> 05040d2 (Initial commit)
- Work with the related departments or parties to promote high quality jobs and to raise standards of living in all counties, instead of just Rural or Suburban counties