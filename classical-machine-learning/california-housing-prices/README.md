# California Housing Prices

## Project Overview

This project explores the California Housing dataset from the 1990 U.S. Census to analyze housing market patterns and build predictive models for median house values. The analysis covers end-to-end machine learning workflow from exploratory analysis to model evaluation.

---

## Objectives

- Analyze geographic and demographic factors affecting housing prices
- Engineer meaningful features to improve model performance
- Build and compare regression models for price prediction
- Identify key drivers of housing value in California

---

## Key Findings

- **Income Correlation**: Median income shows the strongest correlation (0.68) with house value
- **Geographic Impact**: Coastal proximity significantly increases housing prices
- **Feature Engineering**: Custom features like `rooms_per_household` and `bedrooms_per_room` improved model accuracy
- **Model Performance**: Random Forest outperformed Linear Regression and Decision Tree models
- **Ocean Proximity**: Inland areas have systematically lower median house values

---

## Methodology

1. **Data Exploration**: Statistical analysis and geographic visualization of housing distribution
2. **Preprocessing**: Imputation of missing values in `total_bedrooms`, stratified train/test split by income
3. **Feature Engineering**: Created ratio-based features to capture household characteristics
4. **Modeling**: Trained Linear Regression, Decision Tree, and Random Forest regressors
5. **Evaluation**: Cross-validation with RMSE metric for model comparison

---

## Project Structure

| File | Description |
|------|-------------|
| california-housing-prices-solution.ipynb | Complete analysis pipeline with modeling |

---

## Technologies Used

- **Language**: Python 3.x
- **Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn
- **Techniques**: Regression, Cross-Validation, Feature Engineering
- **Environment**: Jupyter Notebook

---

## Dataset

- **Source**: California Housing Prices (1990 Census)
- **Features**: Longitude, latitude, housing median age, total rooms, total bedrooms, population, households, median income, ocean proximity
- **Target**: Median house value
