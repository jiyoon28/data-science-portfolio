# Customer Churn Prediction for StreamWorks

## Project Overview

This project aims to predict customer churn for StreamWorks, a streaming service platform. By analyzing user behavior patterns and subscription data, we develop machine learning models to identify customers at risk of churning, enabling proactive retention strategies.

## Dataset

The dataset contains 1,500 user records with the following features:

| Feature | Description |
|---------|-------------|
| user_id | Unique identifier for each user |
| age | Customer age |
| gender | Customer gender (Male, Female, Other) |
| signup_date | Date of account creation |
| last_active_date | Most recent activity date |
| country | Customer location (USA, UK, Canada, Germany, France, India) |
| subscription_type | Plan type (Basic, Standard, Premium) |
| average_watch_hours | Average monthly viewing hours |
| mobile_app_usage_pct | Percentage of usage via mobile app |
| complaints_raised | Number of complaints filed |
| received_promotions | Whether customer received promotions (Yes/No) |
| referred_by_friend | Whether customer was referred (Yes/No) |
| is_churned | Target variable (1 = Churned, 0 = Retained) |
| monthly_fee | Monthly subscription cost |

## Methodology

### 1. Data Preprocessing

- Handled missing values using appropriate imputation strategies
  - Numerical features: median imputation
  - Categorical features: mode imputation
  - Monthly fee: group mean based on subscription type
- Converted date columns to datetime format
- Dropped rows with missing target variable

### 2. Feature Engineering

- Created `tenure_days`: calculated from signup and last active dates
- Created `is_loyal`: binary flag for customers with tenure > 180 days
- One-hot encoded categorical variables (gender, country, subscription_type)
- Binary encoded Yes/No columns

### 3. Statistical Analysis

Performed hypothesis testing to understand feature-churn relationships:

- Chi-square tests for categorical variables (gender, promotions, referral)
- T-test for continuous variables (average watch hours)

### 4. Handling Class Imbalance with SMOTE

The dataset showed significant class imbalance:
- Before SMOTE: 917 Not Churned (0) vs 280 Churned (1) in training set
- After SMOTE: 917 Not Churned (0) vs 917 Churned (1) - balanced classes

SMOTE (Synthetic Minority Over-sampling Technique) was applied to training data only to prevent data leakage.

### 5. Model Development and Hyperparameter Tuning

**Logistic Regression:**
- GridSearchCV with 5-fold cross-validation
- Parameter grid: C = [0.01, 0.1, 1, 10], penalty = ['l1', 'l2']
- Best parameters: C=0.01, penalty='l2'
- Best CV F1 Score: 0.68
- Feature scaling with StandardScaler

**Random Forest:**
- 100 estimators
- No feature scaling required (tree-based model)

## Results

### Model Performance Comparison

| Model | Test F1 Score | Test ROC-AUC | Accuracy |
|-------|---------------|--------------|----------|
| Logistic Regression | 0.33 | 0.56 | 0.73 |
| Random Forest | 0.23 | 0.58 | - |

### Classification Report (Logistic Regression)

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| Not Churned (0) | 0.79 | 0.76 | 0.78 | 230 |
| Churned (1) | 0.31 | 0.36 | 0.33 | 70 |

### Key Findings

- Logistic Regression slightly outperforms Random Forest on test F1 Score
- Both models achieve similar ROC-AUC scores (~0.56-0.58)
- SMOTE improved model's ability to detect churned customers (36% recall vs near 0% without SMOTE)
- High precision-recall trade-off: models favor majority class prediction
- Class distribution shows imbalance: 76.7% retained vs 23.3% churned

## Technologies Used

- Python 3.x
- pandas, numpy
- scikit-learn
- imbalanced-learn (SMOTE)
- matplotlib, seaborn
- scipy (statistical testing)

## File Structure

```
customer-churn-prediction/
├── customer-churn-prediction.ipynb  # Main analysis notebook
├── streamworks_user_data.csv        # Dataset
└── README.md                        # Project documentation
```

## Future Improvements

- Experiment with additional ensemble methods (XGBoost, LightGBM)
- Further hyperparameter tuning for Random Forest
- Feature importance analysis
- Develop customer segmentation for targeted retention strategies