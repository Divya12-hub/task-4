
# Task 3 — Dashboard Design using Power BI

## Objective
The objective of this task is to design an interactive sales dashboard using **Power BI**. 
The dashboard should allow business stakeholders to monitor key KPIs like Sales, Profit, 
Profit Margin, and YoY growth with filters for Region, Category, and Time.

## Dataset
- File: `sales_data.csv`
- Fields included:
  - OrderID
  - OrderDate
  - Region
  - Category
  - Product
  - Sales
  - Profit
  - Quantity

## Steps Performed
1. Imported dataset (`sales_data.csv`) into Power BI Desktop.
2. Cleaned and transformed data in Power Query:
   - Converted data types (Date, Text, Numbers).
   - Created Year, Month, and Quarter columns.
   - Removed duplicates and handled missing values.
3. Created data model with proper relationships (if needed).
4. Built DAX measures for analysis:
   ```DAX
   Total Sales = SUM('Sales'[Sales])
   Total Profit = SUM('Sales'[Profit])
   Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
   Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Sales'[OrderDate]))
   YoY Growth % = DIVIDE([Total Sales] - [Sales LY], [Sales LY], 0)
   Sales YTD = TOTALYTD([Total Sales], 'Sales'[OrderDate])
   ```
5. Designed dashboard pages with:
   - KPI Cards (Total Sales, Profit, Margin).
   - Line Chart (Sales Trend over Time).
   - Bar Chart (Sales by Category).
   - Map (Sales by Region).
   - Table (Top Products by Sales & Profit).
6. Added interactivity:
   - Slicers for Year, Region, Category.
   - Cross-filtering between visuals.
   - Drillthrough pages for product details.
   - Bookmarks for different views.
7. Applied formatting and design best practices (consistent colors, grid alignment, clear titles).

## Deliverables
- Power BI file: `task3_dashboard.pbix`
- PowerPoint presentation summarizing the dashboard and insights.
- README file (this file).
- Sample dataset: `sales_data.csv`

## Key Insights (example)
- North Region generates the highest sales and profit contribution.
- Technology category consistently performs well across all regions.
- Some furniture items show lower profit margins, requiring pricing review.

## Limitations
- Dataset is a sample and may not reflect real-world complexity.
- Further improvement: add customer-level analysis and forecasting.

## Repository Structure
```
Task3-Dashboard/
│── data/
│   └── sales_data.csv
│── workbook/
│   └── task3_dashboard.pbix
│── ppt/
│   └── task3_dashboard_summary.pptx
│── screenshots/
│   └── dashboard_overview.png
│── README.md
```

---
**Author:** <Your Name>  
**Date:** <YYYY-MM-DD>
