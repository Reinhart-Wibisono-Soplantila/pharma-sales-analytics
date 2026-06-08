# Pharma Sales Demand Analysis (2014–2019)
**Tools:** Microsoft Excel · Power BI · DAX  
**Dataset:** [Pharmacy Sales Data — Kaggle](https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data)

---

## 📋 Project Brief

**Client (Simulated):** Procurement Manager & Sales Team, pharmaceutical distribution company

**Problem Statement:**  
The procurement team frequently faces late restocking due to lack of visibility into demand patterns. The sales team also struggles to identify which product categories to prioritize, resulting in missed opportunities and suboptimal inventory levels.

**Business Questions:**
1. Which drug category has the highest and most consistent demand from 2014–2019?
2. Are there predictable seasonal (monthly) patterns for each category?
3. Which categories are growing, stagnant, or declining — and when did the trend shift?
4. Are there any anomalies or demand spikes in specific periods that require attention?

**Expected Output:**  
Data-driven recommendations to help the procurement team determine restocking timing and the sales team prioritize high-potential product categories.

---

## 📊 Dashboard Preview

### Overview
![Overview](screenshots/overview.png)

### Seasonal Pattern Analysis
![Seasonal Pattern](screenshots/seasonal_pattern.png)

### Annual Trend Analysis
![Annual Trend](screenshots/annual_trend.png)

### Anomaly & Insights
![Anomaly & Insights](screenshots/anomaly_insights.png)

---

## 🔍 Key Findings

### 1. N02BE Dominates 49% of Total Sales Volume — But Growth is Volatile
N02BE (analgesics/antipyretics) consistently holds the largest share of sales volume across all 6 years. However, its growth pattern is unpredictable — peaking in 2016 before dropping sharply in 2017, and never fully recovering. This over-reliance on a single volatile category presents a supply planning risk.

### 2. Clear Seasonal Patterns Found in Key Categories
- **N02BE & N02BA:** Consistent trough in June–July every year, with peak demand in October–February. Aligns with cold/flu season in European markets.
- **R06 (Antihistamines):** Most predictable seasonal pattern — peak consistently in April–May (spring allergy season), trough in December–January. Strongest seasonal signal across all categories.
- **R03:** Trough consistently in July–August, peak in Q4. Second most consistent seasonal pattern.

### 3. BCG Matrix Classification Reveals Strategic Gaps
| BCG Class | Category | Trend |
|---|---|---|
| Cash Cow | N02BE | Volatile |
| Cash Cow | N05B | Declining |
| Question Mark | R03, R06 | Growing |
| Question Mark | M01AB, N05C | Slight Growth |
| Dog | M01AE | Stagnant |
| Dog | N02BA | Declining |

**No Stars category exists** — no category combines high volume with consistent growth. R03 and R06 show the most promising growth trajectories and are underappreciated relative to their potential.

### 4. 2017 Anomaly: Simultaneous Decline Across All Categories (-23% YoY)
All 8 categories declined simultaneously in 2017, with N02BE hit hardest (-30%) and R06 most resilient (-7%). The 2018 rebound of +18% appears strong but is largely a **base effect** — absolute volume in 2018 (62.7) remained below the 2016 pre-anomaly level (68.95), indicating incomplete recovery through 2019. Root cause of the 2017 anomaly cannot be determined from sales data alone; external context (regulatory changes, market disruption) would be required.

---

## 💡 Business Recommendations

1. **Diversify away from N02BE dependency** — its volatility creates procurement risk. Invest in growing R03 and R06 which show consistent, predictable demand.

2. **Implement seasonal procurement calendar** — R06 procurement should increase in February–March ahead of April–May peak. N02BE and N02BA procurement should increase in September ahead of Q4 peak. Reduce orders in May for N02BE/N02BA ahead of June–July trough.

3. **Monitor N05B decline** — as the second-largest category, its consistent downward trend warrants investigation. Is this a market share loss or a category-level decline?

4. **Treat 2018 growth (+18%) with caution** — this is a base effect from 2017's anomaly, not genuine recovery. Volume has not returned to 2016 levels as of 2019.

---

## 🗂️ Data Notes

- **Source:** Point-of-Sale system, individual pharmacy (Serbia/Eastern Europe)
- **Period:** January 2014 – October 2019 (daily granularity)
- **Categories:** 8 ATC drug classifications (M01AB, M01AE, N02BA, N02BE, N05B, N05C, R03, R06)
- **Pre-processing:** Outlier detection and missing value imputation already applied by dataset author
- **Limitation:** 2019 data incomplete (January–October only). Annual comparisons for 2019 use Average Daily Volume to normalize for incomplete period.

---

## 🛠️ Technical Approach

| Stage | Tool | Output |
|---|---|---|
| Data Exploration | Microsoft Excel | Descriptive statistics, conditional formatting heatmaps |
| Seasonal Analysis | Excel Pivot Tables | Monthly avg per category per year, peak/trough tables |
| Trend Analysis | Excel Charts | Multi-series line charts, BCG classification |
| Dashboard | Power BI Desktop | 4-page interactive report |
| DAX Measures | Power BI | Total Volume, Avg Daily Volume, YoY Growth, Best/Worst YoY, Impact Table 2017 |

---

## 📁 Repository Structure

```
pharma-sales-analysis/
│
├── data/
│   └── salesdaily.xlsx
│
├── analysis/
│   └── Brief.docx              # Full analysis documentation (EDA, findings, recommendations)
│
├── dashboard/
│   └── pharma_sales_analysis.pbix
│
├── screenshots/
│   ├── overview.png
│   ├── seasonal_pattern.png
│   ├── annual_trend.png
│   └── anomaly_insights.png
│
└── README.md
```

---

*This project was completed as part of a Data Analyst portfolio. Dataset source: [Milanzdravkovic on Kaggle](https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data).*
