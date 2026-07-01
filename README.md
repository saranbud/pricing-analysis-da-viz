# Specialty Coffee Pricing Analysis

End-to-end pricing analytics project for a specialty coffee business, covering order data from **2023–2025**. Includes a data pipeline notebook and an interactive Databricks Lakeview dashboard.

## Repository Structure

```
pricing-analysis-da-viz/
├── README.md                          # This file
├── pricing_analysis.ipynb             # Data pipeline notebook
└── Specialty Coffee Pricing Analysis  # Lakeview dashboard (.lvdash.json)
    — Strategic Review 2023–2025.lvdash.json
```

## Data Pipeline (`pricing_analysis`)

The notebook ingests raw CSV data from a Unity Catalog Volume and produces three curated tables:

| Output Table | Description |
| --- | --- |
| `Pricing_analysis.data.orders_master` | Denormalized fact table — orders joined with customer and product data, enriched with profitability metrics |
| `Pricing_analysis.data.monthly_performance` | Monthly KPIs aggregated by product category and region |
| `Pricing_analysis.data.product_profitability` | Product-level margins, markups, and volume metrics |

### Source Data

All source files reside in `/Volumes/Pricing_analysis/data/all_datasets/`:
- `Orders_2023.csv`, `Orders_2024.csv`, `Orders_2025.csv` — transaction records
- `customers.csv` — customer master (Region, Join Date)
- `products.csv` — product catalog (Name, Category, Price, Base Cost)

### Key Metrics

- **Gross Profit** = Revenue − COGS
- **Gross Margin %** = (Revenue − COGS) / Revenue × 100
- **Average Selling Price** = Revenue / Quantity
- **Markup %** = (ASP − Base Cost) / Base Cost × 100

## Dashboard

The Lakeview dashboard (`.lvdash.json`) provides a 5-page interactive analysis:

| Page | Focus |
| --- | --- |
| **Executive Summary** | High-level KPIs (revenue, orders, margin, ASP) and top-line trends |
| **Revenue & Growth** | Year-over-year comparisons, monthly revenue by year, markup trends |
| **Product Profitability** | Category-level margins, markup power, ASP comparisons, margin trends over time |
| **Regional Analysis** | East vs. West performance — revenue, margin, orders, and pricing power |
| **Pricing Intelligence** | Deep-dive pricing signals (in development) |

### Dashboard Datasets

The dashboard queries two tables directly:
- `Pricing_analysis.data.orders_master` — for time-series and regional analysis
- `Pricing_analysis.data.product_profitability` — for product-level rankings

## How to Run

1. **Attach compute** — Connect to a Databricks SQL warehouse or serverless compute
2. **Run the notebook** — Execute all cells in `pricing_analysis` to create/refresh the tables
3. **Open the dashboard** — The `.lvdash.json` file renders automatically in the Databricks workspace

## Requirements

- Databricks workspace with Unity Catalog enabled
- Access to the `Pricing_analysis` catalog and `data` schema
- Source CSV files in the specified Volume path
