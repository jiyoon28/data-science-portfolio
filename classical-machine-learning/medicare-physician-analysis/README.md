# Medicare Physician & Other Practitioners — EDA & ML

**Goal**  
Understand what drives **Avg_Mdcr_Pymt_Amt** (average Medicare payment) and build simple models to predict it, using a 50k-row sample for fast iteration.

## Project Motivation

This project analyzes the CMS dataset **“Medicare Physician & Other Practitioners — by Provider and Service”** (50k-row sample) to answer:

1) Do payments differ by **place of service** (F vs O)?
2) Who dominates by **provider type** (volume)?
3) How do **charges, payments, and utilization** move together?
4) Which provider types tend to have **higher payments**?
5) Does **urban–rural context (RUCA)** relate to payments?

Process: **CRISP-DM** — gather → assess → clean → analyze → model → evaluate → visualize.

## Files in the Repository

- `medicare_physician_analysis.ipynb` — Main analysis notebook (EDA → modeling → what-if).
- `data/sample_medicare_physician_small.csv.gz` — 50k-row sample used in the notebook.
- `requirements.txt` — Reproducible environment
- `README.md` — Project overview, results, and references.


## Dataset
- **Source:** [CMS Provider Data](https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider-and-service)
- **Format:** CSV
- **Size:** Large (~millions of rows)

**Key features used**
- Numeric: `Tot_Srvcs`, `Tot_Benes`, `Tot_Bene_Day_Srvcs`, `Avg_Sbmtd_Chrg`
- Categorical: `Rndrng_Prvdr_Type`, `Place_Of_Srvc`
- (Avoid leakage): do **not** feed `Avg_Mdcr_Alowd_Amt`, `Avg_Mdcr_Stdzd_Amt` into the model



## Results Summary
- Skewed payments/charges: heavy right tail → log-scale visuals help.

- Strong drivers: utilization (Tot_Srvcs, Tot_Benes) and Avg_Sbmtd_Chrg; specialty/place matter.

- Models: Random Forest provided more realistic predictions than plain Linear Regression on raw target.

**Blog post:** 
https://medium.com/@moonjiyoon23/who-moves-medicare-spending-da750b090e69

