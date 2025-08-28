# Bank-Customer-Churn-Prediction

End-to-end Python workflow that cleans a **bank-churn dataset**, performs extensive
EDA, and benchmarks five machine-learning models:

1. Logistic Regression + L2 (with grid-search & ROC)
2. K-Nearest Neighbours (grid-search for _k_)
3. Support Vector Machine (hinge-loss, hand-coded SGD, grid-search for _C_)
4. Decision Tree (grid-search for max depth, feature-importance + confusion matrix)
5. Decision Tree + **SMOTE** oversampling to handle class imbalance

All algorithms are implemented **from scratch in NumPy**, showcasing the full
mathematical pipeline—from data standardisation to gradient descent and
cross-validation—without relying on scikit-learn.

---

## Dataset

| File       | Rows × Cols | Notes                                                                                                         |
| ---------- | ----------- | ------------------------------------------------------------------------------------------------------------- |
| `bank.csv` | 10 k × 12   | Credit scores, age, tenure, balance, products, card flag, active flag, salary, geography, gender, churn label |

Categorical fields (country, gender) are one-hot encoded; numeric fields are
standardised.

---
