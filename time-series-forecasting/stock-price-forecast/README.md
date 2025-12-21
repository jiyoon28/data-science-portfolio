# Comparative Analysis of Stock Price Forecasting Models: ARIMA, LSTM, Transformer, and Prophet

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://tensorflow.org)
[![Statsmodels](https://img.shields.io/badge/Statsmodels-ARIMA-green.svg)](https://www.statsmodels.org/)
[![Prophet](https://img.shields.io/badge/Prophet-Facebook-red.svg)](https://facebook.github.io/prophet/)

This repository contains the full implementation and research results for comparing traditional statistical models and modern deep learning architectures in predicting stock market trends.

## 📌 Project Overview
The project evaluates the predictive performance of **ARIMA**, **LSTM**, **Transformer**, and **Prophet** on three distinct stocks: **Amazon (AMZN)**, **Microsoft (MSFT)**, and **ExxonMobil (XOM)**. The study focuses on how different model architectures handle market volatility and non-linear patterns over 1-day and 3-day forecast horizons.



## 🛠 Tech Stack
- **Data Source**: Yahoo Finance (`yfinance`)
- **Preprocessing**: Winsorization (Outlier removal), MinMaxScaler (Normalization)
- **Models**:
  - **ARIMA**: A statistical benchmark for linear time-series patterns.
  - **Prophet**: An additive model designed for seasonality and trend components.
  - **LSTM (RNN)**: Captures long-term temporal dependencies.
  - **Transformer**: Utilizes self-attention mechanisms for global pattern recognition.
- **Evaluation**: Walk-Forward Validation using MAE and RMSE metrics.

## 📊 Key Research Findings
1.  **Short-term Accuracy**: **ARIMA** proved to be highly effective for 1-day predictions, especially in stocks with stable trends like XOM.
2.  **Model Stability**: While error rates generally increased with longer horizons, **LSTM and Transformer** models showed more stability (smaller error increase) for 3-day forecasts compared to Prophet and ARIMA.
3.  **Volatility Impact**: High-volatility stocks (e.g., AMZN) posed significant challenges for all models, with deep learning models requiring more complex tuning to outperform simpler statistical baselines.



## 📂 File Description
- `stock-price-forecasting.ipynb`: Jupyter notebook containing the complete pipeline: data crawling, preprocessing, model training, and comparative visualization.
- `stock-price-forecasting-thesis.pdf`: The full MSc dissertation (Queen Mary University of London) providing the theoretical framework and detailed discussion.


## 📝 Dissertation Details
- **Title**: Comparative Analysis of ARIMA, LSTM, Transformer, and Prophet Models for Stock Price Forecasting
- **Author**: Ji Yoon Moon
- **Institution**: Queen Mary University of London (QMUL)
- **Supervisor**: Prof. Navid Nabijou

---
© 2025 Ji Yoon Moon. This project is for academic and research purposes.