# Final Recommendation
## Part 3 — Regression-Based Business Insights & Model Interpretation
**Student:** Lakshmi S R | **ID:** bitsom_ba_2511906
**To:** Leadership Team — Retail Chain
**Date:** 2026-06-28

---

## Executive Summary

A regression analysis was conducted on 320 store-month records across 80 retail stores. Three models were built and compared. The final multiple regression model explains **79.4% of monthly sales variation** and identifies footfall, marketing spend, and regional location as the strongest drivers of sales performance.

---

## 1. Which Factors Most Strongly Drive Monthly Sales?

Based on the multiple regression model (R² = 0.794):

| Factor | Coefficient | Significance | Impact |
|---|---|---|---|
| **Footfall** | +₹29.30 per customer | ✅ Very Strong | Most important driver |
| **Marketing Spend** | +₹1.14 per ₹1 spent | ✅ Strong | Positive ROI confirmed |
| **South Region** | +₹24,467 vs East | ✅ Significant | Location advantage |
| **West Region** | +₹21,561 vs East | ✅ Significant | Location advantage |
| Staff Count | +₹2,310 per person | ❌ Not significant | Cannot confirm |
| Holiday Flag | +₹12,258 per holiday | ❌ Not significant | Cannot confirm |
| North Region | +₹12,867 vs East | ❌ Not significant | Cannot confirm |

---

## 2. Which Variables Should Leadership Focus On?

### Priority 1 — Footfall (Most Important) 🎯
- **Every 1,000 additional customers = ₹29,300 more sales per month**
- Footfall alone explains 73.6% of sales variation
- **Actions:** Improve store visibility, run footfall-driving promotions, optimize store hours, improve parking/accessibility

### Priority 2 — Marketing Spend 💰
- **Every ₹1 spent on marketing returns ₹1.14 in sales**
- Positive ROI confirmed — marketing pays off
- **Actions:** Maintain or increase marketing budgets, focus on channels that drive footfall, track marketing-to-footfall conversion

### Priority 3 — Regional Strategy 🗺️
- South and West region stores outperform East stores by ₹24,467 and ₹21,561 respectively
- **Actions:** Investigate what South and West stores do differently, replicate successful practices in East and North stores

---

## 3. Which Variables Should NOT Be Over-Interpreted?

| Variable | Why not to over-interpret |
|---|---|
| staff_count | P-value = 0.093 — not statistically significant at 95% confidence |
| holiday_flag | P-value = 0.091 — not statistically significant |
| region_North | P-value = 0.092 — not statistically significant |
| avg_discount_pct | Correlation = -0.09 — almost no relationship with sales |
| customer_rating | Correlation = -0.03 — virtually no relationship with sales |

**Do not make staffing or holiday decisions based solely on this model.**

---

## 4. Business Actions Recommended

### Immediate Actions (High confidence)
1. **Drive footfall** — this is the single biggest lever for sales improvement
   - Run in-store events and promotions
   - Improve store signage and visibility
   - Optimize opening hours based on peak customer times

2. **Maintain marketing investment** — confirmed positive ROI
   - Focus budget on campaigns that directly drive store visits
   - Track footfall as the primary KPI for marketing effectiveness

3. **Learn from South and West stores** — they consistently outperform East
   - Conduct store visits to identify best practices
   - Consider regional manager knowledge-sharing sessions

### Medium-term Actions (Needs further investigation)
4. **Investigate Residential stores** — they consistently underperform model predictions
   - STR-1012, STR-1009, STR-1035, STR-1077 are notable underperformers
   - May need different strategies for residential vs mall vs airport stores

5. **Study Mall stores** — they consistently outperform predictions
   - STR-1028 and STR-1026 exceed predictions by ₹130,000+
   - Identify what drives this outperformance

---

## 5. Risks and Limitations

| Risk | Description |
|---|---|
| Only 4 months of data | Seasonal patterns cannot be fully assessed |
| Correlation ≠ causation | Model shows association, not proof that increasing X causes sales to increase |
| Linear assumption | Real-world sales relationships may not be perfectly linear |
| Missing variables | Store size, competitor activity, local demographics not included |
| Residential store gap | Model systematically overestimates Residential stores — a store_type dummy would improve accuracy |

---

## 6. Why Regression Shows Association But Not Causation

Regression tells us that footfall and sales **move together** — when footfall is high, sales tend to be high. But this does not automatically mean:

> "If we force footfall to increase, sales will definitely increase by ₹29.30 per customer."

**Reasons why causation cannot be assumed:**
1. **Confounding factors** — a third variable (like store location quality) may cause both high footfall AND high sales
2. **Reverse causation** — high sales stores may attract more customers, not the other way around
3. **Selection bias** — stores with high footfall may have other advantages not measured
4. **Limited time period** — 4 months may not represent long-term patterns

**What regression DOES tell us:**
- Footfall is the strongest statistical predictor of sales ✅
- Marketing spend has positive association with sales ✅
- South and West regions show higher sales than East ✅
- These insights are worth acting on — but results should be monitored

---

## 7. Next Steps

1. **Collect more data** — expand to 12+ months for seasonal analysis
2. **Add store_type as dummy variable** — will likely improve model accuracy
3. **Pilot footfall initiatives** — run controlled experiments to confirm causation
4. **Track model performance** — compare actual vs predicted sales monthly
5. **Build store-type specific models** — separate models for Mall, Residential, Airport, High Street
