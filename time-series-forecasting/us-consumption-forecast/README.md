# US Consumption Forecast

## Project Overview

This project models and forecasts quarterly U.S. consumption using time-series analysis in R. Three modeling approaches are compared: a pure moving average benchmark, an automatically selected seasonal ARIMA, and a dynamic regression model (ARIMAX) incorporating macroeconomic regressors.

---

## Models Compared

| Model | Specification | Description |
|-------|---------------|-------------|
| MA(3) | ARIMA(0,0,3) | Pure moving average benchmark |
| Seasonal ARIMA | ARIMA(3,0,0)(2,0,0)[4] | Auto-selected by AICc with seasonal terms |
| ARIMAX | ARIMA(1,1,1)(0,0,1)[4] | Dynamic regression with Income and Unemployment |

---

## Key Findings

- **Best Performance**: ARIMAX model with Income and Unemployment regressors achieved lowest forecast errors
- **Accuracy Metrics**: RMSE = 0.24, MAE = 0.17 on out-of-sample test set
- **External Regressors**: Macroeconomic variables significantly improve consumption forecasts
- **Residual Diagnostics**: All models pass Ljung-Box test for residual autocorrelation

---

## Methodology

1. **Data Splitting**: Train/test split for out-of-sample validation
2. **EDA**: Time series decomposition, ACF/PACF analysis
3. **Model Fitting**: Compare MA(3), auto.arima, and ARIMAX specifications
4. **Diagnostics**: Residual analysis, Ljung-Box test
5. **Forecast Evaluation**: RMSE, MAE, Theil's U on test set

---

## Performance Comparison

| Model | Test RMSE | Test MAE | Ljung-Box p-value |
|-------|-----------|----------|-------------------|
| ARIMA(0,0,3) | 0.2401 | 0.2153 | 0.1297 |
| ARIMA(3,0,0)(2,0,0)[4] | 0.2747 | 0.2482 | 0.8787 |
| ARIMAX | 0.2374 | 0.1687 | 0.1703 |

---

## Project Structure

| File | Description |
|------|-------------|
| us-consumption-forecast.Rmd | R Markdown analysis with code and commentary |
| us-consumption-forecast.pdf | Compiled report with visualizations |

---

## Technologies Used

- **Language**: R
- **Libraries**: forecast, ggplot2, tseries, knitr
- **Techniques**: ARIMA, Seasonal ARIMA, Dynamic Regression (ARIMAX)
- **Output**: R Markdown to PDF
