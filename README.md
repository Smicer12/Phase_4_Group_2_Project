# Phase 4 Group 2 Project....


## Table of contents 
 ### [Business Understanding](#Business-Understanding)
 #### [1.1 Background](##Background)
 #### [1.2 Project Overview](#Project-Overview)
 #### [1.3 Project Question](#Project-Question)
 #### [1.4 Objectives](#Objectives)
 ### [Data Understanding](#Data-Understanding)
 ### [Data Conversion](#Data-Conversion)
 ### [Exploratory data analysis](#Exploratory-data-analysis)
 ### [Training the model](#Training-the-model)
 ### [Conclusion](#Conclusion)
 ### [Recommendations](#Recommendations)
 ### - [Limitations](#Limitations)
 
### Business Problem Understanding
 #### [1.1 Background](##Background)
The real estate market is dynamic and influenced by an array of factors ranging from economic trends and population growth to market sentiment and regulatory changes. Kar-Dak Investments Group recognizes the need to leverage data science techniques to gain a competitive edge in identifying high-potential investment opportunities.

In a constantly evolving real estate landscape, various elements, including economic shifts, population dynamics, market emotions, and regulatory shifts, converge to shape market trends. Acknowledging this complexity, the Kar-Dak Investment Group acknowledges the strategic advantage of harnessing data science methodologies to proactively uncover lucrative investment prospects.
#### [1.2 Project Overview](#Project-Overview)
 The goal of this project is to assist the Kar-Dak Investment Group in identifying the top 5 most promising zip codes for real estate investment opportunities. The analysis will be conducted using the Zillow housing dataset, which encompasses housing data spanning from April 1996 to April 2018. By leveraging this dataset, the project aims to pinpoint zip codes that have demonstrated strong potential for growth and return on investment within the specified time frame.

The primary objective of this project is to facilitate informed real estate investment decisions for the Kar-Dak Investment Group. By leveraging the extensive Zillow housing dataset, which spans from April 1996 to April 2018, the project aims to identify the top 5 most favorable zip codes for potential investment opportunities.
#### [1.3 Project Question](#Project-Question)
This Project aims at answering the question:
 What are the top 5 best zip code areas for the Kar-Dak Investments to consider?
 #### [1.4 Objectives](#Objectives)
 1. To use Time Series Model to determine the top 5 zip codes to invest in
2. To find the top 5 zip codes nationwide with the highest ROI within accepted standard deviation threshold (variability in returns)
3. To Perform Forecasting for Future House Prices
4. Develop time series models to forecast real estate prices for different zip codes over various time horizons.
5. Evaluate the stability and predictability of real estate prices for different zip codes.
6. Determine potential profit margins based on historical data and forecasted price growth.
7. To Combine insights from the above analyses to make a comprehensive recommendation.
8. To effectively identify cities that are optimal for both short-term and long-term investment
9. To create user-friendly interfaces to facilitate easy access to forecast/ predictions and insights.
***
### Data Understanding
The key columns in the dataset are as follows:

`RegionID` This is unique Id for the Regions.

`RegionName` - This is the ranking done based on the size of the Region.

`SizeRank` This field contains the zip code of the Region.

`RegionType` Type of Region is Zip.

`StateName` State.

`City` This column provide the specific City Name of Housing Data.

`Metro` This provide the name of the metro city around that Region.

`County Name` This is the County Name for that Region.

`Months Column` These Columns contains the prices of Region for every month.

***
### Data processing
This stage focussed on data cleaning in preparation for analysis. This included;
* Checking for duplicates.
* Checking for missing values. Columns with very high number of missing values were dropped
* Reshaping from Wide to Long Format

***
### Exploratory Data Analysis
this stage of the analysis focused on such as:

 1. distribution of zip codes.

![zipcode.png](images/zipcode.png)

***
### Modelling



***
### Conclusion


***
### Recommendations


***
### Limitations

