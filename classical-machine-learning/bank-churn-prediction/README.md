# Bank Customer Churn Prediction

## Project Overview

This project implements an end-to-end machine learning pipeline to predict customer churn in the banking sector. All classification algorithms are built from scratch using NumPy, demonstrating the complete mathematical foundations from data preprocessing through model evaluation.

---

## Objectives

- Build binary classification models to predict customer churn
- Implement core ML algorithms without using scikit-learn
- Address class imbalance using SMOTE oversampling
- Compare model performance across multiple algorithms

---

## Key Findings

- **Class Imbalance**: The dataset exhibits significant class imbalance with churned customers being the minority class
- **Feature Importance**: Credit score, age, and account balance are strong predictors of churn
- **Model Comparison**: SVM and Decision Tree achieved highest ROC-AUC scores among tested models
- **SMOTE Impact**: Oversampling improved recall for the minority class while maintaining precision

---

## Models Implemented (From Scratch)

| Model | Technique | Hyperparameter Tuning |
|-------|-----------|----------------------|
| Logistic Regression | L2 Regularization | Grid Search |
| K-Nearest Neighbors | Distance-based classification | Optimal k selection |
| Support Vector Machine | Hinge loss with SGD | Grid Search for C |
| Decision Tree | Information Gain / Gini | Max depth tuning |
| Decision Tree + SMOTE | Oversampling for imbalance | Combined tuning |

---

## Project Structure

| Path | Description |
|------|-------------|
| src/bank-customer-churn-prediction.ipynb | Main implementation notebook |
| src/bank-customer-churn-prediction.pdf | Analysis report |
| data/bank.csv | Customer dataset (10K records, 12 features) |

---

## Technologies Used

- **Language**: Python 3.x
- **Libraries**: NumPy, pandas, matplotlib, seaborn
- **Techniques**: Binary Classification, Cross-Validation, SMOTE, Grid Search
- **Implementation**: All algorithms built from scratch (no scikit-learn)

---

## Dataset

- **Records**: 10,000 customers
- **Features**: Credit score, geography, gender, age, tenure, balance, number of products, credit card status, active member status, estimated salary
- **Target**: Churn indicator (Exited)
