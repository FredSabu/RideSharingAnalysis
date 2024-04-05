---

# RideSharing Data Analysis

## Introduction

This analysis explores the data from a ride-sharing service to understand how various factors like time, weather, and holidays influence service demand. The dataset, courtesy of Keele University, spans from January 2017 to August 2018. The project employs a mix of statistical techniques and machine learning models to extract meaningful insights from the data. 

## Data Preprocessing

### Overview
The preprocessing stage involved converting categorical data into numerical codes, identifying duplicate entries, handling missing values through interpolation, and generating a cleaned dataset, saved as `CarSharing_Preprocessed.csv`.

### Key Steps
- **Categorical to Numerical Conversion:** Variables such as 'season', 'holiday', 'workingday', and 'weather' were converted to numerical codes.
- **Duplicate Identification:** Duplicate rows were identified and removed.
- **Missing Value Handling:** Missing values, especially in 'temp', 'temp_feel', 'humidity', and 'windspeed', were interpolated.
- **Clean Dataset Generation:** The processed data was saved as a new CSV file for subsequent analysis.

## Statistical Analysis

### Spearman's Rank Correlation
This test explored correlations between numerical variables like 'temp', 'temp_feel', 'humidity', and 'windspeed' with the demand, finding moderate to weak correlations. Notably, temperature variables showed a moderate positive correlation with demand, indicating higher temperatures potentially lead to increased ride-sharing usage.

### Mann-Whitney U and Kruskal-Wallis H Tests
These tests assessed the impact of categorical variables on demand. No significant differences were found for 'holiday' and 'workingday' variables, while 'season' and 'weather' showed significant effects on demand, highlighting their importance in ride-sharing usage.

## Time Series Analysis

### Temperature and Humidity in 2017
The analysis revealed clear cyclic patterns for temperature, aligned with seasonal changes, and some variation in humidity levels throughout the year.

### Wind Speed and Demand in 2017
Wind speed trends and demand analysis indicated a decreasing trend in wind speed from the start towards the middle of the year, with demand showing a gradual increasing trend, especially higher during the summer months.

## Heatmaps Analysis

Heatmaps provided detailed insights into the hourly and daily patterns for temperature, humidity, wind speed, and demand in 2017. Notable findings include:
- **Temperature and Humidity:** Displayed expected daily and seasonal patterns, with temperatures peaking during midday and summer months, and humidity showing higher levels during early hours and summer.
- **Wind Speed:** Did not exhibit clear patterns, suggesting the influence of other factors.
- **Demand:** Showed strong daily patterns with peaks during typical commuting hours (rush hour), indicating a cyclical nature tied to daily human activities.

## ARIMA Time Series Forecasting

An ARIMA model was applied to forecast demand, with parameters selected based on ACF and PACF plots and the series' stationarity confirmed through the Augmented Dickey-Fuller test. The model provided forecasts with a Mean Absolute Error (MAE) of approximately 0.2105, a Mean Squared Error (MSE) of roughly 0.053, and a Root Mean Squared Error (RMSE) of about 0.2320.

## Machine Learning Models for Demand Prediction

### Random Forest Regressor vs. Deep Neural Network
- The Random Forest Regressor (RFR) demonstrated superior predictive accuracy over the Deep Neural Network (DNN), evidenced by a lower Mean Squared Error (MSE).
- Feature importance analysis revealed 'hour' as the most influential variable, underscoring the significance of time-of-day patterns in demand prediction.

## Classification and Clustering Analysis

### Classification Models
Three classifiers (K-Nearest Neighbors, Decision Tree, Random Forest) were evaluated for their accuracy in categorizing demand, with the Random Forest classifier achieving the highest accuracy.

### Clustering with K-Means and Agglomerative Clustering
Clustering was applied to temperature data, with K-Means and Agglomerative Clustering algorithms tested across different cluster sizes (k-values). K-Means with k=2 provided the most uniform clustering solution, indicating its effectiveness for this dataset.

## Conclusion
The analysis confirmed that both time and weather play crucial roles in car-sharing demand. The Random Forest Regressor stood out as the most effective tool for predicting this demand. These findings highlight the need to consider a wide range of factors for accurate forecasting in the car-sharing industry.

---
