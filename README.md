# Rice Price Volatility Analysis and Forecasting in North Central Province

## Overview
This repository contains a research project analyzing the impact of fuel price and weather conditions on rice price volatility in North Central province and developing predictive models for rice price forecasting.

## Research Objectives
* Analyze rice price volatility trends and patterns.
* Investigate the relationship between fuel prices and rice prices.
* Examine the impact of weather conditions on rice price fluctuations.
* Develop predictive models for rice price forecasting.
* Develop the dashboard to provide insights to stakeholders.

## Dataset
1. Commodity Dataset(To select Rice Prices in North Central province):
   * Description: The dataset contains commodity prices including rice prices. the dataset contains data from 2004 to 2025. It includes other features such as district, market, longtitude, latitude, usd price etc..
   * Source: The Humanitarian Data Exchange. (URL: https://data.humdata.org/dataset/wfp-food-prices-for-sri-lanka)
   * Time Period: 2015/01/15 - 2025/06/15
   * Key Variables: 'market', 'longtitude', 'latitude', 'price' etc..

2. Weather Dataset:
   * Description: The data set includes weather conditions in Anuradhapura and Polonnaruwa district from 2015 to 2025.
   * Source: Vissual Crossing (URL: https://www.visualcrossing.com/weather-query-builder/)
   * Time Period: 2015 - 2025
   * Key Variables: temp, precip, visibility, windir, solarradiation, solarenergy, uvindex, sealevelpressure, humidity etc..
     
4. Fuel Dataset:
   * Description: The dataset contains fuel prices from 2011 to 2025.
   * Source: Ceylon Petroleum Corporation official website
   * Time Period: 2015 -2015
   * Key Variables: LP 92, LP, 95, LAD, LSD, LIK, LK etc..

## Methodoloy
1. Data preprocessing
   - Data cleaning and handling missing values.
   - Data integration from multiple sources.
   - Scalling data before developing models.
2. Feature Selection Methods
   - Principal Component Analysis (PCA)
   - XGBoost Regressor
3.  Volatility Analysis
     - Support Vector Regression (SVR) model
4.  Price Prediction
   * Machine Learning Models:
     - Linear Regression
     - Random Forest
     - Ensemble model    
5. Model Evaluation:
   - RMSE (Root Mean Square Error)
   - MAE (Mean Absolute Error)
   - MAPE (Mean Absolute Percentage Error)
   - R² Score

## Technologies Used
  * Python 
  * Data Analysis: pandas, numpy
  * Visualization: matplotlib, seaborn, plotly
  * Statistical Analysis: scipy
  * Machine Learning: scikit-learn, xgboost, pycaret

## Key Findings
[This section will be updated with main findings from the research]

### Finding 1: [Brief description]
### Finding 2: [Brief description]
### Finding 3: [Brief description]

## Results

#### Volatility Analysis: [Summary of volatility patterns identified]
### Prediction Accuracy: [Summary of model performance]
### Key Influencing Factors: [List of main factors affecting rice prices]
