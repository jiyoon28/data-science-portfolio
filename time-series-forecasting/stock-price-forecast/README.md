# Stock Price Forecasting: Comparative Analysis

## Project Overview

This project presents a comparative analysis of traditional statistical models and modern deep learning architectures for stock price prediction. The research evaluates ARIMA, LSTM, Transformer, and Prophet models on three distinct stocks with different volatility profiles, examining performance across multiple forecast horizons.

This project was completed as an MSc dissertation at Queen Mary University of London.

---

## Research Objectives

- Compare predictive performance of statistical vs. deep learning approaches
- Evaluate model robustness across stocks with different volatility profiles
- Analyze forecast accuracy degradation over longer prediction horizons
- Identify optimal model selection strategies for different market conditions

---

## Models Evaluated

| Model | Type | Strengths |
|-------|------|-----------|
| ARIMA | Statistical | Linear patterns, short-term accuracy |
| Prophet | Additive | Seasonality, trend decomposition |
| LSTM | Deep Learning | Long-term temporal dependencies |
| Transformer | Deep Learning | Self-attention, global patterns |

---

## Key Research Findings

1. **Short-term Accuracy**: ARIMA proved highly effective for 1-day predictions, especially for stable trend stocks (XOM)
2. **Model Stability**: LSTM and Transformer showed smaller error increases for 3-day forecasts compared to Prophet and ARIMA
3. **Volatility Impact**: High-volatility stocks (AMZN) posed challenges for all models; deep learning required complex tuning to outperform statistical baselines

---

## Methodology

1. **Data Collection**: Yahoo Finance API (yfinance) for AMZN, MSFT, XOM
2. **Preprocessing**: Winsorization for outliers, MinMaxScaler normalization
3. **Evaluation**: Walk-Forward Validation with MAE and RMSE metrics
4. **Horizons**: 1-day and 3-day forecast comparisons

---

## Project Structure

| File | Description |
|------|-------------|
| stock-price-forecasting.ipynb | Complete pipeline: data crawling, preprocessing, training, visualization |
| stock-price-forecasting-thesis.pdf | Full MSc dissertation with theoretical framework |

---

## Technologies Used

- **Language**: Python 3.8+
- **Deep Learning**: TensorFlow 2.x
- **Statistical Models**: Statsmodels (ARIMA), Prophet
- **Data Source**: Yahoo Finance (yfinance)
- **Evaluation**: Walk-Forward Validation, MAE, RMSE

---

## Academic Details

- **Title**: Comparative Analysis of ARIMA, LSTM, Transformer, and Prophet Models for Stock Price Forecasting
- **Author**: Ji Yoon Moon
- **Institution**: Queen Mary University of London
- **Supervisor**: Prof. Navid Nabijou