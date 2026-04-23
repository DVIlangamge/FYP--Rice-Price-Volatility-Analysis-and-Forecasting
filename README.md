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
   * Time Period: 2015/01/01 - 2025/09/31
   * Key Variables: temp, precip, visibility, windir, solarradiation, solarenergy, uvindex, sealevelpressure, humidity etc..
     
4. Fuel Dataset:
   * Description: The dataset contains fuel prices from 2011 to 2025.
   * Source: Ceylon Petroleum Corporation official website (URL: https://ceypetco.gov.lk/historical-prices/)
   * Time Period: 2011/01/01 - 2025/10/01
   * Key Variables: LP 92, LP, 95, LAD, LSD, LIK, LK etc..

## Methodoloy
1. Data preprocessing
   - Data cleaning and handling missing values.
   - Data integration from multiple sources.
   - Scalling data before developing models.
2. Feature Selection Methods
   - XGBoost Regressor
3.  Volatility Analysis
   - ADF Test
   - Cointegration Test
   - GARCH Model
5.  Price Prediction
   * Machine Learning Models:
     - Support Vector Regression (SVR) model
     - Linear Regression
     - Random Forest Regression
     - Ensemble model(AdaBoost, XGBoost, LightGBM)
5. Model Evaluation
   - RMSE (Root Mean Square Error)
   - MAE (Mean Absolute Error)
   - MSE (Mean Square Error)
   - R² Score
<img width="728" height="948" alt="image" src="https://github.com/user-attachments/assets/095f45f0-48f1-4b48-9ba3-fa92ed960a7e" /> Proposed Methodology

## Technologies Used
  * Python 
  * Data Analysis: Pandas, Numpy
  * Visualization: Matplotlib, Seaborn, Plotly
  * Statistical Analysis: Scipy, statsmodel
  * Machine Learning: Scikit-Learn, XGBoost, PyCaret
  * Dashboard Creation: Power BI
  * Environment: Google Colab

## Key Findings

### Finding 1: 
The key influence rice price is the fuel price. Sometimes, when the fuel price increases, rice prices permenently increases.
### Finding 2: 
The fluctuations of rice prices not only depends on climate factors, but also on external factors such as soil temperature, soil moisture, evapotranspiration, policies, fertility prices.
### Finding 3: 
EGARCH results proves that rice price is a non-stationary variable without a stable relationship with any other variable

## Results

### Volatility Analysis:
ADF tests for rice price were done considering the following Hypothesis.
  #### H0: The log_price data are stationary. 
  #### H1: The log_price data are non-stationary. 
When the p_value for ADF test is less than 0.05, null hypothesis can not be be rejected. For original rice price, the null hypothesis was rejected as the result was greater than 0.05. ADF test was once again done to log_price difference, focusing on pure fluctuations and considering the same hypothesis. Here, the p_value was recorded as 3.588117006105815e-13, which is sigmificantly lower than 0.05. Therfore, the null hypothesis was rejected.

The correlation between log_price and log_fuel was 0.67. The cointegration test results considereing log_price and log_fuel was 0.11628289945004383. Hypothesis for this test are, 
  #### H0: The log_price and log_fuel are stationary. 
  #### H1:The log_prices and log_fuel data are non-stationary.
The null hypothesis for this is rejected as 0.11628289945004383 > 0.05. Correlation results shows that there is a moderately positive correlation between log_price and log_fuel. However, the relationship seems to be driven by short-term shocks. Therfore, it can be said that, log_price and log_fuel data do not have a long, stable relationship

GARCH models were used to further analyze rice price volatility. In the study, GARCH (1,1), GJR-GARCH(1,1,1) and EGARCH(1,1) were implemented. The best model with the highest log-likelihood, lowest AIC and BIC values was EGARCH. The conditional volitilities calculated using EGARCH model, indicates that it does not have any serial correlation in the squared standardized residuals. This validtes the  the future price uncertainty.

### Prediction Results: 
  #### Best Pipeline Approach: Data + Standardization + Transformation
  |Module|MAE|MSE|RMSE|R2|
  |------|---|---|----|--|
  |SVR|0.0524|0.004|0.0635|0.9262|
  |LR|0.4056|0.245|0.495|-3.491|
  |RFR|0.0621|0.007|0.0835|0.8722|
  |Ensemble Module|0.0622|0.007|0.0836|0.8718|
  |LSTM|11.205|211.905|14.556|-2.893|

  By comparing the results for machine learning models, SVR model performed the best with low MAE, MSE, RMSE values and higher R-squared value.
### Key Influencing Factors: 
<img width="597" height="363" alt="weather impact" src="https://github.com/user-attachments/assets/d40d09f9-ba54-4117-882b-e681529c2834" />
The key influence graph generated using Power BI for price 'lag_6' variable, shows the key influencing weather variables for rice price fluctuations.

# Power BI dashboard interface
<img width="1367" height="745" alt="Power BI dashboard" src="https://github.com/user-attachments/assets/3a9485ab-1e2d-4db0-bc06-e2ab0136e886" />

