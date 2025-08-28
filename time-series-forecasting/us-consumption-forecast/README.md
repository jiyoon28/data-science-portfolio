# US-Consumption-Forecast

Quarterly U.S. consumption is modelled and forecast using three
time-series approaches in **R**:

1. **ARIMA(0,0,3)** – pure MA(3) benchmark
2. **ARIMA(3,0,0)(2,0,0)[4]** – seasonal/non-seasonal AR terms selected by `auto.arima`
3. **Dynamic regression (ARIMAX)** with Income & Unemployment as external regressors
   - Error term: ARIMA(1,1,1)(0,0,1)[4]

The ARIMAX model delivers the best out-of-sample accuracy
(RMSE ≈ 0.24, MAE ≈ 0.17).
