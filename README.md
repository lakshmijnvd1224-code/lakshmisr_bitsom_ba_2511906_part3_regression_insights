# Part 3: Regression-Based Business Insights & Model Interpretation

**Student:** Lakshmi S R
**Student ID:** bitsom_ba_2511906
**Program:** BITSoM Business Analytics with Gen & Agentic AI
**Repository:** lakshmisr_bitsom_ba_2511906_part3_regression_insights

---

## Business Problem Summary

A retail chain wants to understand what factors drive monthly sales performance across stores. Leadership is considering actions such as increasing marketing spend, improving inventory, changing discounting strategy, reallocating staff, and prioritizing certain store types or regions. Regression analysis was used to identify which factors are most strongly associated with monthly sales.

---

## Dataset Description

| Property | Details |
|---|---|
| File | business_regression_data.xlsx |
| Records | 320 (80 stores × 4 months) |
| Columns | 14 |
| Date Range | January 2025 — April 2025 |
| Stores | 80 unique retail stores |

---

## Dependent and Independent Variables

**Dependent Variable (Y):** monthly_sales

**Independent Variables (X) used in regression:**

| Variable | Type | Correlation with Sales |
|---|---|---|
| footfall | Numerical | 0.86 — Very Strong |
| staff_count | Numerical | 0.81 — Very Strong |
| marketing_spend | Numerical | 0.41 — Moderate |
| holiday_flag | Numerical (0/1) | 0.20 — Weak |
| region | Categorical → Dummy | Varies by region |
| store_type | Categorical → Dummy | Created but not in final model |

**Variables excluded:**
- avg_discount_pct (correlation = -0.09)
- customer_rating (correlation = -0.03)
- inventory_availability_pct (correlation = 0.11)
- competitor_distance_km (correlation = -0.11)

---

## Regression Approach

1. Calculated correlations between all variables and monthly_sales
2. Selected variables with correlation > 0.15 as candidates
3. Ran 2 simple regression models (one variable at a time)
4. Ran 1 multiple regression model (7 variables including dummies)
5. Compared models using R-squared, standard error, and p-values
6. Selected multiple regression as final model

---

## Dummy Variable Approach

**Region dummies created:**
- region_North (1 = North, 0 = otherwise)
- region_South (1 = South, 0 = otherwise)
- region_West (1 = West, 0 = otherwise)
- **Reference category: East**

**Store type dummies created (in workbook, not used in final model):**
- store_High Street
- store_Mall
- store_Residential
- **Reference category: Airport**

---

## Model Comparison Summary

| Model | Variables | R-Squared | Best For |
|---|---|---|---|
| Model 1 — Simple | footfall | 0.736 | Quick footfall insight |
| Model 2 — Simple | marketing_spend | 0.167 | Marketing ROI check |
| Model 3 — Multiple | 7 variables | 0.794 | Full business analysis |

---

## Final Model Selected

**Model 3 — Multiple Regression** with R² = 0.794

**Equation:**
```
Monthly Sales = 370,748
              + (29.30 × footfall)
              + (2,310 × staff_count)
              + (1.14 × marketing_spend)
              + (12,258 × holiday_flag)
              + (12,867 × region_North)
              + (24,467 × region_South)
              + (21,561 × region_West)
```

**Significant variables:** footfall, marketing_spend, region_South, region_West

---

## Business Recommendation

1. **Footfall is the #1 driver** — every 1,000 more customers = ₹29,300 more sales
2. **Marketing spend shows positive ROI** — ₹1 spent returns ₹1.14 in sales
3. **South and West regions outperform East** — learn and replicate their practices
4. **Residential stores consistently underperform** — needs targeted investigation
5. **Mall stores outperform predictions** — identify and scale their success factors

---

## Assumptions and Limitations

1. Only 4 months of data — seasonal trends not fully captured
2. Regression shows association, not causation
3. Linear relationships assumed — may not hold for all variables
4. Store size, local demographics, and competitor activity not included
5. Residential store type shows systematic overestimation — store_type dummies would improve model

---

## Screenshots Included

| File | Shows |
|---|---|
| simple_regression_output.png | Simple regression output (Model 1 — footfall) |
| multiple_regression_output.png | Multiple regression output (Model 3) |
| residuals_preview.png | Top 5 positive and negative residuals |
| model_comparison_preview.png | Full model comparison table |
