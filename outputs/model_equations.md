# Model Equations
## Part 3 — Regression-Based Business Insights & Model Interpretation
**Student:** Lakshmi S R | **ID:** bitsom_ba_2511906
**Date:** 2026-06-28

---

## 1. Simple Regression Equations

### Model 1 — monthly_sales vs footfall

```
Monthly Sales = 446,410.58 + (35.678 × footfall)
```

| Component | Value | Meaning |
|---|---|---|
| Intercept | 446,410.58 | Base sales with zero footfall |
| footfall coefficient | 35.678 | Each additional customer adds ₹35.68 in sales |
| R-squared | 0.736 | Footfall explains 73.6% of sales variation |
| P-value | 4.75E-94 | Extremely significant |

**Business meaning:** For every 1,000 additional customers visiting the store, monthly sales increase by approximately ₹35,678.

---

### Model 2 — monthly_sales vs marketing_spend

```
Monthly Sales = 560,777.35 + (2.130 × marketing_spend)
```

| Component | Value | Meaning |
|---|---|---|
| Intercept | 560,777.35 | Base sales with zero marketing spend |
| marketing_spend coefficient | 2.130 | Every ₹1 spent on marketing returns ₹2.13 in sales |
| R-squared | 0.167 | Marketing spend explains only 16.7% of sales variation |
| P-value | 2.48E-14 | Significant but weak predictor |

**Business meaning:** Marketing spend shows positive ROI (₹2.13 return per ₹1 invested), but it is a weak standalone predictor of sales.

---

## 2. Multiple Regression Equation

```
Monthly Sales = 370,748.28
              + (29.299 × footfall)
              + (2,309.87 × staff_count)
              + (1.137 × marketing_spend)
              + (12,258.29 × holiday_flag)
              + (12,867.03 × region_North)
              + (24,466.78 × region_South)
              + (21,561.45 × region_West)
```

---

## 3. Coefficient Explanation

| Variable | Coefficient | Significant? | Business Meaning |
|---|---|---|---|
| Intercept | 370,748.28 | ✅ Yes | Base monthly sales for an East region store with all other factors at zero |
| footfall | 29.299 | ✅ Yes | Each additional customer → +₹29.30 in monthly sales |
| staff_count | 2,309.87 | ❌ No (p=0.093) | Each additional staff member → +₹2,310 (not statistically reliable) |
| marketing_spend | 1.137 | ✅ Yes | Every ₹1 of marketing spend → +₹1.14 in sales |
| holiday_flag | 12,258.29 | ❌ No (p=0.091) | Holiday months → +₹12,258 (not statistically reliable) |
| region_North | 12,867.03 | ❌ No (p=0.092) | North stores sell ₹12,867 more than East (not reliable) |
| region_South | 24,466.78 | ✅ Yes | South stores sell ₹24,467 MORE than East stores |
| region_West | 21,561.45 | ✅ Yes | West stores sell ₹21,561 MORE than East stores |

---

## 4. Dummy Variable Explanation

### Region Dummy Variables

| Variable | Value = 1 | Value = 0 | Reference Category |
|---|---|---|---|
| region_North | Store is in North | Store is NOT in North | East |
| region_South | Store is in South | Store is NOT in South | East |
| region_West | Store is in West | Store is NOT in West | East |

**Reference category: EAST**

East region is the baseline. All other regions are compared against East:
- South stores earn ₹24,467 MORE than East stores per month
- West stores earn ₹21,561 MORE than East stores per month
- North stores earn ₹12,867 MORE than East stores (not significant)

### Why East is the reference category
East was chosen as the reference category because it is the first alphabetically and serves as a natural baseline. Dropping one category prevents the dummy variable trap (perfect multicollinearity).

### Store Type Dummy Variables
Store type dummies were created in the Dummy Variables sheet but not included in the final regression model. The reference category would have been Airport if included.

---

## 5. Worked Example

**Predict monthly sales for a South region store with:**
- footfall = 7,000
- staff_count = 18
- marketing_spend = ₹60,000
- No holiday (holiday_flag = 0)
- South region (region_South = 1, others = 0)

```
Sales = 370,748.28
      + (29.299 × 7,000)     = +205,093
      + (2,309.87 × 18)      = +41,578
      + (1.137 × 60,000)     = +68,220
      + (12,258.29 × 0)      = 0
      + (12,867.03 × 0)      = 0  ← not North
      + (24,466.78 × 1)      = +24,467  ← South
      + (21,561.45 × 0)      = 0  ← not West

Predicted Monthly Sales = ₹710,106
```

---

## 6. Final Model Selected

**Model 3 — Multiple Regression** is the final selected model.

**Reasons:**
1. Highest R-squared (79.4%) — explains most sales variation
2. Lowest standard error (₹47,621) — most accurate predictions
3. Captures multiple business levers simultaneously
4. Identifies statistically significant regional differences
5. Provides actionable insights for leadership decisions
