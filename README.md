# Power BI Sales Analysis 📊

An advanced Power BI project demonstrating enterprise-level data modelling, DAX measure development, and interactive business intelligence reporting. Built independently as a self-taught Power BI project.

---

## Live Dashboard

<!-- ADD: screenshot of main dashboard page here -->
<!-- Tip: In Power BI Desktop, File → Export → Export to PDF or screenshot each page -->

---

## Key Findings

- **$8.9M revenue recovery opportunity** identified from 174 unprofitable transactions
- Optimised data model reduced file size by **60%** using star schema architecture
- Interactive what-if analysis enabling price modelling across **6 products, 5 segments, and 6 countries**

---

## Dashboard Pages

<!-- ADD: screenshot of each page with brief caption -->

### 1. Executive Summary
<!-- ADD: screenshot -->
Overview of key KPIs: total revenue, profit margin, units sold, YoY growth

### 2. Sales Analysis
<!-- ADD: screenshot -->
Breakdown by product, segment, and country with drill-through capability

### 3. What-If Price Modelling
<!-- ADD: screenshot -->
Dynamic parameter sliders enabling scenario analysis across products and markets

### 4. Profitability Analysis
<!-- ADD: screenshot -->
Identification of unprofitable transactions and pricing recommendations

---

## Data Model

### Star Schema Architecture
- **1 Fact Table:** Sales transactions
- **4 Dimension Tables:** Products, Customers, Geography, Date
- **Result:** 60% reduction in model size vs flat table

<!-- ADD: screenshot of model view from Power BI Desktop -->

---

## DAX Measures (15+)

Key measures developed:

```DAX
-- Total Revenue
Total Revenue = SUMX(Sales, Sales[Units] * Sales[Sale Price])

-- Profit Margin %
Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0)

-- What-If Price Adjustment
Adjusted Revenue = 
    SUMX(
        Sales,
        Sales[Units] * Sales[Sale Price] * (1 + 'Price Adjustment'[Price Adjustment Value])
    )

-- Unprofitable Transactions
Unprofitable Count = COUNTROWS(FILTER(Sales, [Transaction Profit] < 0))
```

<!-- ADD: list any other notable measures -->

---

## Tech Stack

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)

---

## Files

```
power-bi-sales-analysis/
├── sales_analysis.pbix     # Power BI report file
├── data/
│   └── sales_data.xlsx     # Source data  <!-- ADD if including raw data -->
├── images/
│   ├── dashboard.png       <!-- ADD screenshots -->
│   ├── model_view.png
│   └── what_if.png
└── README.md
```

---

## How to View

1. Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Clone this repo
3. Open `sales_analysis.pbix`

---

## What I Learned

- Star schema design and why it outperforms flat tables
- Writing complex DAX measures (SUMX, CALCULATE, DIVIDE, FILTER)
- What-if parameter implementation for scenario analysis
- Identifying business insights from transaction-level data
- Self-teaching Power BI from scratch to production-quality output

---

*Part of my journey from Operations Manager to ML Engineer. Follow along on [Dev.to](https://dev.to/jemhrice)*
