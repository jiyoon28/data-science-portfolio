# Medicare Physician Analysis

## Project Overview

This project analyzes the CMS "Medicare Physician and Other Practitioners" dataset to understand the factors driving Medicare payment amounts. Using a 50,000-row sample, the analysis explores relationships between provider characteristics, service utilization, and payment patterns through exploratory data analysis and predictive modeling.

---

## Research Questions

1. Do payments differ by place of service (Facility vs. Office)?
2. Which provider types dominate by service volume?
3. How do charges, payments, and utilization metrics correlate?
4. Which provider specialties tend to have higher payments?
5. Does urban-rural context (RUCA classification) relate to payment amounts?

---

## Key Findings

- **Payment Distribution**: Heavy right-tail skew in payments/charges; log-scale transformations reveal clearer patterns
- **Strong Predictors**: Service utilization (Tot_Srvcs, Tot_Benes) and submitted charges drive payment amounts
- **Specialty Impact**: Provider specialty significantly affects average payment, with surgical specialties showing higher averages
- **Model Performance**: Random Forest provided more realistic predictions than plain Linear Regression

---

## Methodology

This project follows the CRISP-DM framework:
1. Data gathering and quality assessment
2. Data cleaning and preprocessing
3. Exploratory data analysis with visualizations
4. Feature engineering and model training
5. Evaluation and interpretation

---

## Project Structure

| File | Description |
|------|-------------|
| medicare_physician_analysis.ipynb | Main analysis notebook (EDA, modeling, insights) |
| requirements.txt | Python dependencies |

---

## Technologies Used

- **Language**: Python 3.x
- **Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn
- **Techniques**: EDA, Random Forest, Linear Regression
- **Framework**: CRISP-DM

---

## Dataset

- **Source**: [CMS Provider Data](https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider-and-service)
- **Sample Size**: 50,000 rows
- **Key Features**: Tot_Srvcs, Tot_Benes, Avg_Sbmtd_Chrg, Rndrng_Prvdr_Type, Place_Of_Srvc

---

## Related Publication

[Medium Blog Post: Who Moves Medicare Spending?](https://medium.com/@moonjiyoon23/who-moves-medicare-spending-da750b090e69)
