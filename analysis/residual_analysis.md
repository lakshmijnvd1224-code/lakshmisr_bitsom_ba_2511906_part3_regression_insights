# Residual Analysis
## Part 3 — Regression-Based Business Insights & Model Interpretation
**Student:** Lakshmi S R | **ID:** bitsom_ba_2511906
**Final Model:** Multiple Regression (Model 3)
**Date:** 2026-06-28

---

## 1. What is a Residual?

A residual is the difference between the actual sales value and the value predicted by the regression model:

```
Residual = Actual Sales − Predicted Sales

Positive residual (+) → Store sold MORE than predicted → model underestimated
Negative residual (-) → Store sold LESS than predicted → model overestimated
Near zero            → Model predicted accurately
```

---

## 2. Residual Summary Statistics

| Metric | Value |
|---|---|
| Total observations | 320 |
| Standard Error of model | ₹47,621 |
| Largest positive residual | +₹136,124 |
| Largest negative residual | -₹144,712 |
| Most residuals fall within | ±₹50,000 |

---

## 3. Top 5 Largest Positive Residuals

*(Stores where actual sales EXCEEDED predictions)*

| Observation | Store ID | Region | Store Type | Actual Sales | Predicted Sales | Residual |
|---|---|---|---|---|---|---|
| 112 | STR-1028 | East | Mall | 713,611 | 577,487 | +136,124 |
| 104 | STR-1026 | East | Mall | 625,514 | 494,328 | +131,186 |
| 202 | STR-1051 | East | Airport | 787,716 | 676,770 | +110,946 |
| 298 | STR-1075 | West | High Street | 763,162 | 660,670 | +102,493 |
| 8 | STR-1002 | East | High Street | 850,164 | 752,354 | +97,810 |

### Business Interpretation — Positive Residuals

- **East region dominates** — 3 out of 5 stores are in East region
- **Mall stores outperform predictions** — 2 Mall stores appear in top 5
- These stores have **hidden advantages** not captured by the model
- Possible reasons: prime locations, loyal customer base, better store management, local events
- **Business action:** Study these stores to understand what they do differently and replicate best practices

---

## 4. Top 5 Largest Negative Residuals

*(Stores where actual sales FELL SHORT of predictions)*

| Observation | Store ID | Region | Store Type | Actual Sales | Predicted Sales | Residual |
|---|---|---|---|---|---|---|
| 45 | STR-1012 | West | Residential | 595,468 | 740,180 | -144,712 |
| 67 | STR-1017 | West | High Street | 685,379 | 823,061 | -137,682 |
| 33 | STR-1009 | North | Residential | 641,865 | 770,452 | -128,587 |
| 137 | STR-1035 | South | Residential | 633,638 | 753,604 | -119,966 |
| 306 | STR-1077 | South | Residential | 538,376 | 654,686 | -116,310 |

### Business Interpretation — Negative Residuals

- **Residential stores dominate** — 4 out of 5 stores are Residential type
- These stores consistently **underperform** relative to their predicted sales
- Possible reasons: lower footfall in residential areas, different customer buying patterns, operational issues
- **Business action:** Investigate why Residential stores underperform — consider targeted interventions like local marketing or adjusted staffing

---

## 5. Under-prediction vs Over-prediction Patterns

### Model tends to UNDERESTIMATE (positive residuals):
- **Mall stores** — actual sales higher than predicted
- **East region stores** — consistently outperform model predictions
- **Airport stores** — unique customer base not fully captured

### Model tends to OVERESTIMATE (negative residuals):
- **Residential stores** — 4 out of 5 worst performers are Residential
- Model gives too much credit to footfall and marketing in residential areas
- Residential shoppers may behave differently from mall or airport shoppers

---

## 6. What Residuals Tell Us About Model Quality

| Observation | Implication |
|---|---|
| Large positive residuals in Mall stores | Model needs a Mall-specific variable |
| Large negative residuals in Residential stores | Residential areas have unique factors not captured |
| No clear regional pattern in negatives | Regional dummies are partially working |
| Standard error = ₹47,621 | On average, predictions are off by ₹47,621 per month |

---

## 7. Recommendations Based on Residual Analysis

1. **Add store_type dummy variables** to the model — current model only has region dummies, not store type dummies. This would likely reduce residuals for Mall and Residential stores significantly.
2. **Investigate STR-1012 and STR-1017** — largest underperformers. Could indicate operational issues or data quality problems.
3. **Study STR-1028 and STR-1026** (East Mall stores) — largest overperformers. Identify success factors for replication.
4. **Consider separate models** for different store types — Mall, Residential, Airport, and High Street may have fundamentally different sales drivers.
