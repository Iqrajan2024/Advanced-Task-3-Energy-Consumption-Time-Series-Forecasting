# Energy Consumption Time Series Forecasting
Forecasting household electricity usage using ARIMA, Prophet, and XGBoost models.

## Overview
This project focuses on short-term energy consumption forecasting using historical household power consumption data. By leveraging classical statistical methods and machine learning, we explore seasonal patterns and make accurate daily forecasts. 

## Objective
- Predict daily household energy usage based on historical patterns.
- Compare the performance of ARIMA, Prophet, and XGBoost models.
- Evaluate models based on metrics like MAE, MSE, and RMSE.

## Dataset Description
- **Source**: UCI Machine Learning Repository – Household Power Consumption Dataset
- **Time Range**: December 2006 to December 2008
- **Frequency**: Minute-level data, resampled to daily averages
- **Main Variable**: `Global_active_power` (kilowatt)
- **Features Extracted**:
  - Lag features (1, 2, 3, 7, 14 days)
  - Rolling means and standard deviations (7-day and 30-day)
  - Time-based features (day of week, month, quarter, year, weekend indicator)

## My Approach
1. **Data Cleaning & Preparation**  
   - Converted datetime fields
   - Handled missing values
   - Resampled to daily averages

2. **Exploratory Data Analysis**  
   - Visualized seasonal trends and volatility
   - Decomposed time series into trend, seasonality, and residuals

3. **Stationarity Testing**  
   - Conducted Augmented Dickey-Fuller (ADF) test
   - Applied differencing to achieve stationarity

4. **Modeling**  
   - Tuned ARIMA parameters using grid search on (p,d,q)
   - Trained Prophet model with additive seasonality
   - Used XGBoost with engineered features and time-based cross-validation
5. **Evaluation**  
   - Compared models using MAE, MSE, and RMSE
   - Visualized actual vs. predicted values for all models
     
## Key Insights
- **ARIMA (6,1,7)** model achieved the lowest RMSE (**0.316**), outperforming Prophet and XGBoost.
- **Prophet** handled seasonality components well and offered high interpretability.
- **XGBoost** leveraged time-based features effectively, producing competitive forecasts.
- Clear **weekly and monthly seasonality** patterns were identified in the data.
- Feature engineering and proper resampling significantly improved model performance.

## Technologies Used
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Statsmodels (ARIMA, ADF test)
- Facebook Prophet
- XGBoost
- Scikit-learn (Metrics, train/test split)

## Skills Demonstrated
- Time Series Preprocessing and Resampling
- Stationarity Testing and Differencing
- Feature Engineering (lags, rolling stats, date parts)
- Model Selection and Hyperparameter Tuning
- Forecasting with ARIMA, Prophet, and XGBoost
- Evaluation using MAE, MSE, RMSE
- Data Visualization and Interpretation

##  Results Summary

| Model   | MAE    | MSE     | RMSE    |
|---------|--------|---------|---------|
| ARIMA   | 0.224  | 0.100   | **0.316** |
| Prophet | 0.240  | 0.106   | 0.326   |
| XGBoost | 0.245  | 0.105   | 0.325   |
