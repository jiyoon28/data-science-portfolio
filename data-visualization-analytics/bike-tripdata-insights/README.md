# California Housing Prices Project 🏡

## Overview
This project analyzes the **California Housing Prices dataset** using Python.  
It is divided into two main parts: **data wrangling** and **data visualization**.  
The ultimate goal is to prepare and explore the dataset for further modeling and insights.

---

## Contents

### Part I: Data Wrangling
- Load the dataset into pandas DataFrame
- Inspect and clean the data
- Handle missing values (e.g., in `total_bedrooms`)
- Create new features such as:
  - `rooms_per_household`
  - `bedrooms_per_room`
  - `population_per_household`
- Apply stratified sampling based on income categories

### Part II: Data Visualization
- Explore feature distributions with histograms
- Generate correlation heatmaps
- Create scatter plots (e.g., house value vs. income, geographic location)
- Visualize the impact of engineered features
- Identify strongest predictors of housing value

---

## Key Insights
- `median_income` has the strongest correlation with `median_house_value`.
- Engineered features improve the understanding of housing market patterns.
- Geographic visualization reveals coastal areas with higher house prices.

---

## Next Steps
- Build and evaluate regression models (Linear Regression, Decision Tree, Random Forest, etc.)
- Perform hyperparameter tuning for better accuracy
- Extend analysis with advanced visualization libraries (e.g., Plotly, Seaborn)

---

## Requirements
- Python 3.x
- pandas, numpy
- matplotlib, seaborn
- scikit-learn