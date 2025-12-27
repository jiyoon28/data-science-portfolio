# Customer Churn Prediction for StreamWorks

## Project Overview

This project aims to predict customer churn for StreamWorks, a streaming service platform. By analyzing user behavior patterns and subscription data, we develop a machine learning model to identify customers at risk of churning, enabling proactive retention strategies.

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

### 2. Feature Engineering

- Created `tenure_days`: calculated from signup and last active dates
- Created `is_loyal`: binary flag for customers with tenure > 180 days
- One-hot encoded categorical variables (gender, country, subscription_type)
- Binary encoded Yes/No columns

### 3. Statistical Analysis

Performed hypothesis testing to understand feature-churn relationships:

- **Chi-square tests** for categorical variables (gender, promotions, referral)
- **T-test** for continuous variables (average watch hours)

### 4. Model Development

- **Algorithm**: Logistic Regression
- **Feature Scaling**: StandardScaler
- **Class Imbalance Handling**: SMOTE (Synthetic Minority Over-sampling Technique)
- **Train/Test Split**: 80/20 with stratification

## Key Findings

- Class distribution shows imbalance: 76.6% retained vs 23.4% churned
- Statistical tests indicate no significant relationship between individual categorical features and churn
- SMOTE improves model performance on minority class (churned customers)

## Model Evaluation Metrics

- Confusion Matrix
- Precision, Recall, F1-Score
- ROC-AUC Score

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

- Experiment with ensemble methods (Random Forest, XGBoost)
- Hyperparameter tuning using GridSearchCV
- Feature importance analysis
- Develop customer segmentation for targeted retention strategies

## Author

Jiyoon Moon
