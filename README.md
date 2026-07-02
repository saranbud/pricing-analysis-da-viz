# ☕ Specialty Coffee Pricing Analysis — Strategic Review (2023–2025)

## The Business Question

> *"Are we pricing our coffee products profitably across regions, and how has our pricing strategy performed over three years?"*

This project answers that question by analyzing **4,400+ orders** across a specialty coffee company's full product catalog from single-origin beans and subscriptions to grinders and accessories spanning **2023 to 2025**.

---

## Key Findings

| Insight | Detail |
| --- | --- |
| **Revenue Growth** | Tracked year-over-year revenue trends across 5 product categories to identify growth drivers |
| **Margin Health** | Computed gross margins at both the product and category level to flag underperforming SKUs |
| **Regional Pricing Power** | Compared East vs. West region performance to uncover pricing inconsistencies and market opportunities |
| **Product Profitability Ranking** | Identified top and bottom 10 products by realized gross margin, surfacing items where discounts erode list-price margins |
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

<img width="1872" height="657" alt="image" src="https://github.com/user-attachments/assets/7eb8a436-a147-46c5-8f71-edb4a17a7db7" />


### Revenue & Growth
> Year-over-year revenue comparison, monthly overlays, and markup trend analysis.

<img width="1672" height="787" alt="image" src="https://github.com/user-attachments/assets/3ed59d67-0640-44bd-afae-86c9d28b5fbe" />


### Product Profitability
> Category-level margins, markup power, and how each category's profitability has evolved over time.

<img width="1872" height="833" alt="image" src="https://github.com/user-attachments/assets/a528ee30-9901-42cd-812c-00d1eb20d5c4" />


### Regional Analysis
> East vs. West — revenue, margins, order volume, and pricing power comparison.

<img width="1867" height="827" alt="image" src="https://github.com/user-attachments/assets/4a35b43d-cf75-488b-b50d-c2eda27dcfa4" />

---

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

This project was built as a pricing analytics case study demonstrating the ability to take raw transactional data, engineer it into business-ready datasets, and present strategic insights through interactive visualizations, the full analytics lifecycle from data to decision.

## Recommendations

These are the actions I'd bring to a strategy meeting based on what the data is telling us:

### 1. Double Down on Subscriptions
Subscriptions are the clear winner here. They have the **highest margin (65%)**, the **highest markup (200%)**, and they bring in recurring revenue. If I were advising this business, I'd push hard on subscriber acquisition through loyalty discounts, referral programs, and trial-to-paid conversion campaigns. The margin profile means even aggressive discounting on the first month still pays off long-term.

### 2. Reprice or Restructure Merchandise
Merchandise is the weakest category by every profitability metric. A few things I'd explore:
- Review the bottom-performing SKUs and ask whether they're worth keeping at current prices
- Test price increases on branded items like mugs and tumblers where brand loyalty gives us room
- Alternatively, reposition merchandise as a customer acquisition tool rather than a profit center (bundle it with equipment)

### 3. Fix the Data Quality Issue (Null Regions)
The regional charts show a "null" region appearing in the data. That means some customers have no region assigned, which makes our segmentation less reliable. What can help here:
- Audit the customer source file for missing values
- Add validation rules so new records can't come in without a region
- Backfill existing records using shipping address or order history

### 4. Expand Volume in Underperforming Regions
Good news: margins are consistent across regions. That means the gap between West and the others is purely a volume problem, not a pricing one. The business can invest in marketing for North and South without worrying about diluting margins. The playbook that works in the West should translate.

### 5. Introduce Seasonal Pricing
Monthly markup swings between **120% and 170%**, and that's not intentional. A deliberate seasonal pricing calendar could:
- Capture more margin during natural demand spikes (Oct through Dec shows clear peaks)
- Use targeted discounts in slow months to keep volume up without blanket markdowns

### 6. Create Cross-Category Bundles
**Grinders & Brewers** drive the most revenue but sit at moderate margins. **Subscriptions** and **Consumables** have great margins but lower ticket prices. The obvious play is bundling: "Buy a grinder, get 3 months of subscription at 20% off." This increases order value, moves customers into recurring products, and creates switching costs through equipment lock-in.
