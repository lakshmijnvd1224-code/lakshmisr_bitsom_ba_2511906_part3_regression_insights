# Model Comparison
## Part 3 — Regression-Based Business Insights & Model Interpretation
**Student:** Lakshmi S R | **ID:** bitsom_ba_2511906
**Date:** 2026-06-28

---

## Overview

Three regression models were built to identify factors driving monthly sales across 80 retail stores over 4 months (320 observations).

---

## Model Comparison Table

| Item | Model 1 — Simple | Model 2 — Simple | Model 3 — Multiple |
|---|---|---|---|
| **Model Name** | Simple Regression 1 | Simple Regression 2 | Multiple Regression |
| **Dependent Variable** | monthly_sales | monthly_sales | monthly_sales |
| **Independent Variables** | footfall | marketing_spend | footfall, staff_count, marketing_spend, holiday_flag, region_North, region_South, region_West |
| **R-Squared** | 0.736 | 0.167 | 0.794 |
| **Adjusted R-Squared** | 0.735 | 0.165 | 0.789 |
| **Standard Error** | 53,374 | 94,846 | 47,621 |
| **Observations** | 320 | 320 | 320 |
| **Significant Variables** | footfall | marketing_spend | footfall, marketing_spend, region_South, region_West |
| **Non-Significant Variables** | None | None | staff_count, holiday_flag, region_North |
| **P-value (main variable)** | 4.75E-94 | 2.48E-14 | 4.07E-23 (footfall) |

---

## R-Squared Comparison

```
Model 1 (footfall only):        R² = 73.6%  ██████████████░░░░░░
Model 2 (marketing_spend only): R² = 16.7%  ███░░░░░░░░░░░░░░░░░
Model 3 (7 variables):          R² = 79.4%  ████████████████░░░░
```

**Model 3 explains the most variation in monthly sales (79.4%).**

---

## Significant Variables

### Model 1
- **footfall** (p = 4.75E-94) — extremely significant

### Model 2
- **marketing_spend** (p = 2.48E-14) — significant

### Model 3
- **footfall** (p = 4.07E-23) — most important driver
- **marketing_spend** (p = 4.92E-15) — significant
- **region_South** (p = 0.0017) — significant
- **region_West** (p = 0.0019) — significant
- **staff_count** (p = 0.093) — not significant
- **holiday_flag** (p = 0.091) — not significant
- **region_North** (p = 0.092) — not significant

---

## Business Usefulness

### Model 1 — High usefulness for footfall planning
- Footfall alone explains 73.6% of sales variation
- Simple and easy to communicate to leadership
- Limitation: ignores marketing, staffing, and regional effects

### Model 2 — Moderate usefulness for marketing decisions
- Shows marketing spend has positive ROI (₹2.13 return per ₹1 spent)
- Very weak predictor — only 16.7% of sales explained
- Limitation: cannot be used alone for sales forecasting

### Model 3 — Best overall model for business decisions
- Explains 79.4% of sales variation
- Captures multiple factors simultaneously
- Identifies regional differences (South and West outperform East)
- Limitation: assumes linear relationships, does not capture store size or seasonal trends

---

## Final Model Selected

**Model 3 — Multiple Regression** is the final selected model because:
1. Highest R-squared (79.4%)
2. Lowest standard error (₹47,621)
3. Uses multiple business-relevant factors
4. Includes dummy variables for regional analysis
5. Provides actionable insights across multiple levers

---

## Limitations

| Model | Limitation |
|---|---|
| Model 1 | Only 1 variable — cannot capture full picture of sales drivers |
| Model 2 | Very low R² — marketing spend alone is a poor predictor |
| Model 3 | Assumes linear relationships — real-world sales may be non-linear |
| All models | Based on only 4 months of data — seasonal patterns not fully captured |
| All models | Correlation ≠ causation — regression shows association, not proof of cause |
