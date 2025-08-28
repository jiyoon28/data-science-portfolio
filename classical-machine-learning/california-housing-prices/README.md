# California Housing Prices Solution 🏡

## Overview
This notebook explores the **California Housing Prices dataset** (1990 U.S. Census data).  
The goal is to **analyze the housing market and build predictive models** for median house value.

---

## Contents
1. **Data Loading & Exploration**
   - Basic statistics and visualizations
   - Geographic scatter plots of housing prices
   - Correlation analysis with median income, rooms, and population

2. **Data Preprocessing**
   - Handling missing values in `total_bedrooms`
   - Feature engineering (e.g., `rooms_per_household`, `bedrooms_per_room`)
   - Train/test split with stratified sampling on income

3. **Modeling**
   - Linear Regression as a baseline
   - Decision Tree and Random Forest regressors
   - Model evaluation with RMSE and cross-validation

4. **Results & Insights**
   - `median_income` shows the strongest correlation with house value
   - Feature-engineered variables improve model performance
   - Random Forest performed best among tested models

---

## Key Learnings
- Feature engineering is crucial for improving predictive accuracy  
- Cross-validation provides more reliable model evaluation  
- Geographic and demographic features strongly influence housing prices  

---

## Next Steps
- Try Gradient Boosting / XGBoost models  
- Hyperparameter tuning for Random Forest  
- Deploy results with interactive dashboards (e.g., using Plotly or Streamlit)  
