# Mobile Sales Dashboard

A Power BI dashboard analysing mobile sales performance across 19 Indian cities, 5 brands, 15 models, and 4 payment methods — covering 3,835 transactions over a full calendar year.

---

## Short Description

A Power BI dashboard built to track mobile sales performance across India. It covers total revenue, units sold, transactions, and customer ratings — broken down by brand, model, city, age group, payment method, and time period.

---

## Business Objective

The goal of this dashboard is to help sales teams and regional managers monitor mobile sales across India. It answers questions like which cities and brands drive the most revenue, which age groups are the highest value customers, how payment methods are distributed, and when sales peak throughout the year.

---

## Tools Used

- Power BI Desktop
- Power Query
- DAX
- Auto-generated Date Table

---

## Data Source

**File:** `Mobile_Sales_Data.xlsx` — 3,835 transactions across 5 brands, 15 models, and 19 cities.

| Column | Description |
|--------|-------------|
| Transaction ID | Unique identifier for each sale |
| Brand | Apple / Samsung / OnePlus / Vivo / Xiaomi |
| Mobile Model | Specific model name |
| Units Sold | Number of units per transaction |
| Price Per Unit | Selling price in ₹ |
| Customer Age | Age of the customer (18–59) |
| City | Indian city of sale |
| Payment Method | UPI / Credit Card / Debit Card / Cash |
| Customer Ratings | Satisfaction rating (1–5) |
| Day / Month / Year | Date fields for time intelligence |

> This is a multi-brand Indian mobile sales dataset covering Apple, Samsung, OnePlus, Vivo, and Xiaomi.

---

## DAX Measures

| Measure | Expression | Description |
|---------|------------|-------------|
| Total Sales | `SUMX(Sales_Data, Sales_Data[Price Per Unit] * Sales_Data[Units Sold])` | Revenue as price × units per row |
| Total Quantity | `SUM(Sales_Data[Units Sold])` | Total units sold |
| Transactions | `COUNTROWS(Sales_Data)` | Total transaction count |
| Avg Price Per Unit | `AVERAGE(Sales_Data[Price Per Unit])` | Average selling price |
| MoM Sales Change | `DIVIDE([Total Sales] - CALCULATE([Total Sales], PREVIOUSMONTH('Date'[Date])), CALCULATE([Total Sales], PREVIOUSMONTH('Date'[Date])))` | Month-over-month revenue change % |

---

## What I Built

- 5 KPI cards — Total Sales, Total Quantity, Transactions, Avg Price Per Unit, Avg Customer Rating
- Total Sales by City — interactive map across 19 Indian cities
- Total Quantity by Month — line chart showing monthly sales trend
- Brand Revenue Comparison — bar chart across all 5 brands
- Customer Age Segmentation — revenue and sales by age group
- Top 5 Mobile Models by Sales — table with revenue, quantity, and transactions
- Transactions by Payment Method — bar chart
- Customer Ratings Distribution — bar chart
- Total Sales by Day of Week — bar chart
- Month slicer and Mobile Model dropdown filter

---

## Key Numbers

- Total Sales: ₹769M
- Total Quantity: 19K units
- Transactions: 4K
- Avg Price Per Unit: ₹40K
- Avg Customer Rating: 3.70 / 5

---

## Key Findings

- iPhone SE leads revenue at ₹59.6M, followed by OnePlus Nord (₹57.9M) and Galaxy Note 20 (₹56.0M)
- 45–59 age group drives 35% of total revenue — highest value customer segment
- All 5 brands are closely competitive — no single brand dominates
- Payment methods are nearly evenly split across UPI, credit card, cash, and debit card
- July peaks at 1,700 units; February dips to 1,451 — useful for inventory planning
- Saturday consistently outperforms other days of the week

---

## How to Use

1. Download `Motorola_Sales_Dashboard.pbit` and `Mobile_Sales_Data.xlsx`
2. Open the `.pbit` file in Power BI Desktop
3. When prompted, connect to `Mobile_Sales_Data.xlsx` as the data source
4. Use the Month slicer and Mobile Model dropdown to filter the dashboard
5. Use the map visual to drill into specific cities

> The `.pbit` file does not contain data — connect to `Mobile_Sales_Data.xlsx` on first open.

---

## Dashboard Preview

![Mobile Sales Dashboard](Snapshot%20of%20Mobile%20Sales%20Dashboard.png)
