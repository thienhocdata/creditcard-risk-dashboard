# 📊 Credit Card Transaction Risk Analysis Dashboard

A data analysis project that builds a behavioral `RiskScore` system to identify suspicious credit card transactions from an unlabeled dataset.

---

## Overview

The dataset contains no ground-truth fraud labels (`fraud`, `is_fraud`, `Class`, etc.), so the approach focuses on:

> Analyzing transactions across multiple risk-related dimensions and constructing a `RiskScore` to flag transactions that warrant review or indicate high suspicion.

- `NeedReview = 1` if `RiskScore >= 2` — transaction requires monitoring
- `PotentialFraud = 1` if `RiskScore >= 3` — high-suspicion transaction
- `PotentialFraud` is a **proxy label**, not a verified fraud label from a financial institution

---

## Pipeline

```
Raw Data
→ Data Validation & Merging
→ Feature Engineering
→ Pre-RiskScore EDA
→ Credit Limit Utilization Analysis
→ RiskScore Construction (distribution-adjusted thresholds)
→ Post-RiskScore EDA
→ ANOVA
→ Chi-square Tests
→ Linear Regression
→ Feature Audit (circular reasoning check)
→ Logistic Regression
→ Decision Tree
→ Model Comparison
```

---

## Repository Structure

| File | Description |
|------|-------------|
| `creditcard_risk_analysis.ipynb` | Main notebook — Final Code V2 |
| `cc_info.csv` | Card information (credit limits, location) |
| `transactions.csv` | Raw transaction data |
| `creditcard_merged_basic.csv` | Merged dataset with engineered features |
| `creditcard_risk_dashboard_v2.html` | Interactive dashboard (exported from notebook) |
| `Do_an_THKTPTDL_creditcard.pptx` | Presentation slides |

---

## Key Design Decisions

- `amount` extreme threshold uses **P99** instead of P95
- `amount_to_limit_high` threshold uses **P99** instead of a hard 0.50 cutoff
- `daily_cum_to_limit_high` threshold uses **P99** instead of a hard 0.80 cutoff
- Separate analysis confirms that transactions at or near the credit limit are genuinely rare

---

## Tech Stack

Python 3 · pandas · numpy · matplotlib · scipy · statsmodels · scikit-learn
