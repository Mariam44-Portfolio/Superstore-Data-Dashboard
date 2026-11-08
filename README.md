# Superstore Data and Dashboard - Power BI
## From Raw Excel Data to Interactive Dashboard

## 📋 Project Overview
Cleaned Superstore raw Excel data and built an interactive Power BI dashboard to track sales, profit, orders and performance by Category, Region, Quarter and Segment.

## 📂 PART 1 - The Raw Data (Excel)
File: `Superstore raw`

Columns cleaned:
Row ID | Order ID | Order Date | Ship Date | Ship Mode | Customer ID | Customer Name | Segment | Country | City | State | Postal Code | Region | Product ID | Category | Sub-Category | Product Name | Sales | Quantity | Discount | Profit

Cleaning done in Power Query:
- Removed duplicates / blank rows
- Fixed Date format for Order Date & Ship Date
- Changed Sales, Profit, Quantity to Numbers
- Split / Trimmed Customer Name, City, State
- Removed extra spaces in Segment, Region, Category

## 📊 PART 2 - The Dashboard (Power BI)
Page: `superstore Dashboard`

### KPIs
- Total Sales: $2.30M
- Total Profit: $286.36K
- Total Order: 5K
- Profit Margin: 12.47%

### Visuals
- Total Sales by Category - Donut: Technology biggest, then Furniture, Office Supplies $741.74K (32.25%)
- Total Sales by Region - Bar: West highest, then East, Central, South
- Total Sales by Quarter - Line: Sales rising from Qtr 1 to Qtr 4, from $0.4M to $0.8M+
- Total Profit by Product Name - Bar: Canon Image, Fellowes, etc. - top products by profit
- Total Sales and Total Profit by Category - Column: Technology has highest sales AND profit, Furniture has sales but low profit
- Total Sales by Segment - Donut: Consumer $1.16M (50.3%), Corporate $0.71M (30.74%), Home Office $0.43M (18.71%)
- Filters: Year 2011, 2012, 2013, 2014 + Region: Central, East, South, West

### Insights
1. Technology is the star - highest sales and profit.
2. Furniture sells a lot but profit is low - discount / cost problem.
3. Consumer segment is 50% of sales - main customers.
4. West region leads sales.
5. Sales grow every quarter - business is growing.

## 🧠 DAX Formulas Used
```dax
Total Sales = SUM(Superstore[Sales])

Total Profit = SUM(Superstore[Profit])

Total Order = DISTINCTCOUNT(Superstore[Order ID])

Profit Margin % = DIVIDE([Total Profit], [Total Sales])

Total Quantity = SUM(Superstore[Quantity])
