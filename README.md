# Sales Performance Dashboard (Apr 2023–Apr 2025)

## 1. Business Goal
Build an end-to-end sales performance dashboard to monitor Sales, Profit, Margin, Orders, Customers, and identify drivers across time, region, segment, and product.

## 2. Dataset
- Source: sale_data.csv (order-level)
- Coverage: Apr 2023 → Apr 2025 (partial 2025)
- Key fields: Order Date, Sales, Profit, Order ID, Customer ID, Region, Segment, Product Name

## 3. Data Modeling
- Created a Date table and relationship: Date[Date] → sale_data[Order Date]
- Marked Date table as Date Table
- Implemented English month labels using SWITCH to avoid locale issues

## 4. KPI Definitions (DAX)
- Total Sales = SUM(sale_data[Sales])
- Total Profit = SUM(sale_data[Profit])
- Total Orders = DISTINCTCOUNT(sale_data[Order ID])
- Total Customers = DISTINCTCOUNT(sale_data[Customer ID])
- Margin = Total Profit / Total Sales
- AOV = Total Sales / Total Orders
- YoY / MoM measures using SAMEPERIODLASTYEAR and DATEADD

## 5. Dashboard Pages
### Overview
- KPI summary
- Monthly trend
- Sales by segment & region
- Top products

### Deep Dive
- YoY/MoM KPI cards
- Sales vs Sales LY trend
- Region/segment breakdown
- Top products ranked by profit (Top 10)

## 6. Key Findings
- Sales YoY: ~+90.7%; Profit YoY: ~+87.0% (latest period in selection)
- Segment mix is balanced (~33% each)
- Regions are relatively even in sales (~$3.0M–$3.2M)

## 7. Recommendations
- Set margin guardrails & alerts for early detection
- Manage product portfolio based on profit ranking (Top 10)
- Normalize partial months (Sales/day) for fair YoY comparisons

## 8. Limitations & Next Steps
- 2025 is partial; consider excluding partial month or using normalized KPIs
- Add discount/returns/channel/cost data for deeper margin diagnostics
