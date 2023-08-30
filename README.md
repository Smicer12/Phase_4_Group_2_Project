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
 ### [Limitations](#Limitations)
 
### Business Problem Understanding
 #### [1.1 Background](##Background)
The real estate market is dynamic and influenced by an array of factors ranging from economic trends and population growth to market sentiment and regulatory changes. Kar-Dak Investments Group recognizes the need to leverage data science techniques to gain a competitive edge in identifying high-potential investment opportunities.

In a constantly evolving real estate landscape, various elements, including economic shifts, population dynamics, market emotions, and regulatory shifts, converge to shape market trends. Acknowledging this complexity, the Kar-Dak Investment Group acknowledges the strategic advantage of harnessing data science methodologies to proactively uncover lucrative investment prospects.
#### [1.2 Problem statement](Problem-statement)
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
In this section, we will do the following to get more insights about our dataset before proceeding to subsequent steps.

1. Import the Libraries
2. Load and Explore the Time Series Data
3. Inspect the Data Types
4. Inspect the column values
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

The dataset covers a significant time period (April 1996 to April 2018), allowing for the exploration of long-term trends and capturing various market conditions. It provides a valuable resource for conducting time series analysis and developing predictive models to forecast future stock prices

***
### Exploratory Data Analysis
this stage of the analysis focused on such as:

 1. distribution of zip codes.

![zipcode.png](images/zipcode.png)
Based on the bar graph above, this shows that Los Angeles is the most popular county with around 70000 zipcodes.Most of the other counties range between 30000 and 50000 zipcodes.

2. Average housing price pattern/trend over the years, that is, from year 1996 to 2018

![price.png](images/price.png)
The graph shows that the average housing price has been increasing steadily over the years, with a dip between 2007 and 2012, during the financial crisis. Since then, the average housing price has rebounded and continued to rise

3. poperty value and distribution
![property_value.png](images/property_value.png)

Zipcode 10021,10011, 10014, 10128 in New York has properties with the highest value, followed by 94027 in California and 81611 in Colorado, and the other remaining Zipcodes range between 2 to 3 Million.

![state_price.png](images/state_price.png)

As observed, the percentage of return on investents for the top ten states had a crash in 2008 to 2012 and then from there they all have an upward linear trend. This also depicts the rising trent has been from 2012 onwards meaning 2018 remains highest in terms of investments returns.

***
### Data preprocessing
Prior to modeling, a thorough assessment of data stationarity will be conducted using the following methods:

1. Dickey-Fuller Test: The Dickey-Fuller test will be employed to assess the stationarity of the data. This statistical test helps determine if a unit root is present in the series, which is indicative of non-stationarity.

2. Rolling Mean Analysis: Additionally, a rolling mean analysis will be performed. This involves calculating the mean over a sliding window of observations. Fluctuations in the rolling mean indicate non-stationarity.

In cases where the data is identified as non-stationary, a differencing technique will be applied. Differencing involves computing the difference between consecutive observations. This process helps transform the data into a stationary form, enabling more accurate modeling and analysis.


***
### Modelling
The goal of modeling is to provide a conceptual and organized framework that helps in making predictions or decisions based on the data.
Since the aim is to identify the top five zipcodes to invest in, five different models for each of the top five zipcodes were developed to help investers forecast their prices and thus give the them clear path to make informed decision.

#### [Baseline Model - ARIMA](##Baseline-Model--ARIMA)
ARIMA is a popular time series forecasting model that combines autoregressive, differencing, and moving average components.

Its use for price prediction is justified due to its ability to capture time-dependent patterns, handle nonlinear relationships, address stationarity, provide interpretability, and its well-established framework in time series analysis.
An ARIMA model was used to fit multiple time series data corresponding to different zip codes as shown below:

below is a plot of Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) of the dataset to determine the appropriate values of the ARIMA model parameters ("p" "d"and "q").

![ACF_PCF.png](images/ACF_PCF.png)

#### [Model Selection](##Model-Selection)
The best-fitting model is specified as ARIMA(2,0,3)(0,0,0)[0] intercept, indicating that it includes autoregressive (AR) terms, moving average (MA) terms, and an intercept.

The model was fitted using 158 observations from February 1, 2005, to April
1, 2018.

The p-values associated with the coefficients indicate whether they are statistically significant. Small p-values suggest significant effects.

#### [Model Fitting](##Model-Fitting)
An ARIMA model was fitted to multiple time series data corresponding to different zip codes.
***
#### [Model Evaluation](##Model-Evaluation)
The model's performance was evaluated using Mean Squared Error. it was noted to have an MSE of 0.0036754150523843564. This tells us that our monthly returns would be off by 0.0037% if this model is used Which is good thing since it is not off by much.

####  [Forecasting for for Top five Zipcodes)](##Forecasting-for-Top-five-Zipcodes)
Once the model was evaluated and deemed satisfactory, it was used to make future predictions as below.
![forecasting.png](images/forecasting.png)
Based on the above graph, we can conclude that investor decide to invest in any of the above zipcodes apart
from 94301 which does not seem to have a positive return on investment.
### Conclusion


***
### Recommendations


***
### Limitations

