# ☕ Specialty Coffee Pricing Analysis — Strategic Review (2023–2025)

## The Business Question

> *"Are we pricing our coffee products profitably across regions, and how has our pricing strategy performed over three years?"*

This project answers that question by analyzing **4,400+ orders** across a specialty coffee company's full product catalog — from single-origin beans and subscriptions to grinders and accessories — spanning **2023 to 2025**.

---

## Key Findings

| Insight | Detail |
| --- | --- |
| **Revenue Growth** | Tracked year-over-year revenue trends across 5 product categories to identify growth drivers |
| **Margin Health** | Computed gross margins at both the product and category level to flag underperforming SKUs |
| **Regional Pricing Power** | Compared East vs. West region performance to uncover pricing inconsistencies and market opportunities |
| **Product Profitability Ranking** | Identified top and bottom 10 products by realized gross margin — surfacing items where discounts erode list-price margins |
| **Pricing Trends Over Time** | Monthly markup and selling price trends reveal whether pricing discipline held or slipped |

---

## What This Project Demonstrates

- **Data Engineering** — Built an automated pipeline that ingests raw CSV data, joins 5 source tables, and produces clean analytical datasets
- **Business Analysis** — Translated raw transactions into actionable KPIs: gross margin, markup, average selling price, and profitability rankings
- **Data Visualization** — Designed a 5-page interactive dashboard for executive-level storytelling
- **Cloud Analytics** — End-to-end implementation on Databricks using SQL, Unity Catalog, and Lakeview dashboards

---

## Dashboard Preview

### Executive Summary
> Total revenue, order volume, gross margin, and selling price KPIs with year-over-year and monthly trend charts.

![Executive Summary](images/01_executive_summary.png)

### Revenue & Growth
> Year-over-year revenue comparison, monthly overlays, and markup trend analysis.

![Revenue & Growth](images/02_revenue_growth.png)

### Product Profitability
> Category-level margins, markup power, and how each category's profitability has evolved over time.

![Product Profitability](images/03_product_profitability.png)

### Regional Analysis
> East vs. West — revenue, margins, order volume, and pricing power comparison.

![Regional Analysis](images/04_regional_analysis.png)

### Pricing Intelligence
> Product-level deep-dive: bottom 10 margin products and discount impact analysis.

![Pricing Intelligence](images/05_pricing_intelligence.png)

---

## Project Structure

```
pricing-analysis-da-viz/
├── README.md                              ← You are here
├── pricing_analysis.ipynb                 ← Data pipeline (SQL notebook)
├── pricing_dashboard.lvdash.json          ← Interactive dashboard definition
└── images/                                ← Dashboard screenshots
    ├── 01_executive_summary.png
    ├── 02_revenue_growth.png
    ├── 03_product_profitability.png
    ├── 04_regional_analysis.png
    └── 05_pricing_intelligence.png
```

---

## Data & Methodology

**Data Sources:** 3 years of order transactions, a customer master table (with region), and a product catalog (with list prices and base costs).

**Approach:**
1. **Consolidate** — Union yearly order files into a single master dataset
2. **Enrich** — Join with customer and product data to add context (region, category, cost basis)
3. **Compute** — Derive profitability metrics: gross profit, margin %, markup %, and average selling price
4. **Aggregate** — Build summary views by month/category/region for trend analysis and by product for profitability ranking
5. **Visualize** — Present findings in an interactive dashboard designed for non-technical stakeholders

---

## Tools & Technologies

- **Databricks** — Cloud data platform (compute, storage, orchestration)
- **SQL** — All data transformations and metric calculations
- **Unity Catalog** — Data governance and table management
- **Lakeview Dashboards** — Interactive business intelligence visualizations
- **Git** — Version control and collaboration

---

## About

This project was built as a pricing analytics case study demonstrating the ability to take raw transactional data, engineer it into business-ready datasets, and present strategic insights through interactive visualizations — the full analytics lifecycle from data to decision.
