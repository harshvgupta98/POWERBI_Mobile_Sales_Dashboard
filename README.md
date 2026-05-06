# 📱 Mobile Sales Dashboard

A dynamic, interactive Power BI dashboard analysing mobile sales performance across 19 Indian cities, 5 brands, 15 models, and 4 payment methods — covering 3,835 transactions over a full calendar year.

---

## 📌 Short Description / Purpose

The **Mobile Sales Dashboard** is a visually engaging Power BI report designed to help sales teams and business leaders monitor mobile sales performance across India. The dashboard tracks total revenue, quantity, transactions, and customer ratings — enabling data-driven decisions around product strategy, regional focus, customer segmentation, and payment trends.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Main data visualisation platform |
| **Power Query** | Data transformation and cleaning layer |
| **DAX (Data Analysis Expressions)** | Calculated measures for KPIs and time intelligence |
| **Power BI Map Visual** | Geographic sales distribution across India |
| **Auto-generated Date Table** | Enables time intelligence (MoM comparisons) |
| **File Format** | `.pbit` (Power BI Template) + `.xlsx` (source data) |

---

## 🧮 DAX Measures

| Measure | Expression | Description |
|---------|------------|-------------|
| `Total Sales` | `SUMX(Sales_Data, Sales_Data[Price Per Unit] * Sales_Data[Units Sold])` | Revenue as price × units per row |
| `Total Quantity` | `SUM(Sales_Data[Units Sold])` | Total units sold |
| `Transactions` | `COUNTROWS(Sales_Data)` | Total transaction count |
| `Avg Price Per Unit` | `AVERAGE(Sales_Data[Price Per Unit])` | Average selling price |
| `MoM Sales Change` | `DIVIDE([Total Sales] - CALCULATE([Total Sales], PREVIOUSMONTH('Date'[Date])), CALCULATE([Total Sales], PREVIOUSMONTH('Date'[Date])))` | Month-over-month revenue change % |
| `Attrition_Rate` | — | N/A for this project |

> KPI cards use explicit measures throughout — no implicit aggregations.

---

## 📂 Data Source

**Source**: Indian mobile sales transactional dataset  
**Scope**: 3,835 transactions | 5 brands | 15 models | 19 cities | Full calendar year

### Brands Covered
Apple · Samsung · OnePlus · Vivo · Xiaomi

> ⚠️ Note: This is a **multi-brand** Indian mobile sales dataset. The dashboard analyses all five brands comparatively — it is not limited to any single brand.

---

## 📖 Data Dictionary

### Sales_Data (Fact Table)

| Column | Type | Description |
|--------|------|-------------|
| `Transaction ID` | Int | Unique identifier for each sales transaction |
| `Day` | Int | Day of the month |
| `Month` | Int | Month number (1–12) |
| `Year` | Int | Calendar year |
| `Day Name` | String | Day of week (Monday–Sunday) |
| `Brand` | String | Mobile brand (Apple, Samsung, OnePlus, Vivo, Xiaomi) |
| `Mobile Model` | String | Specific model (e.g., iPhone SE, Galaxy Note 20) |
| `Units Sold` | Int | Number of units sold per transaction |
| `Price Per Unit` | Decimal | Selling price per unit (₹) |
| `Customer Name` | String | Customer name |
| `Customer Age` | Int | Customer age (18–59 years) |
| `City` | String | Indian city of sale (19 cities) |
| `Payment Method` | String | UPI / Credit Card / Debit Card / Cash |
| `Customer Ratings` | Int | Satisfaction rating (1=Lowest, 5=Highest) |

### Date Table (Auto-generated)

| Column | Description |
|--------|-------------|
| `Date` | Full date value |
| `Year` | Calendar year |
| `MonthNo` | Month number (1–12) |
| `Month` | Month name |
| `QuarterNo` | Quarter number (1–4) |
| `Quarter` | Quarter label (Q1–Q4) |
| `Day` | Day of the month |

---

## ✨ Features / Highlights

### 🔴 Business Problem

Sales teams and regional managers struggle to quickly answer:

- Which cities and brands are driving the most revenue?
- Which customer age groups represent the highest value segment?
- Are there seasonal trends in monthly sales volume?
- Which payment methods are most preferred?
- How does customer satisfaction vary across brands and models?

### 🎯 Dashboard Goals

- Give leadership a real-time view of revenue, quantity, and transactions at a glance
- Enable regional analysis through an interactive map of sales across 19 Indian cities
- Support product decisions by highlighting top-performing brands and models
- Uncover customer demographic patterns through age segmentation
- Track satisfaction trends through ratings distribution

---

## 🖼️ Walkthrough of Key Visuals

### Key KPIs (Top Row)
- **Total Sales**: ₹769M
- **Total Quantity**: 19K units
- **Transactions**: 4K
- **Avg Price Per Unit**: ₹40K
- **Avg Customer Rating**: 3.70 / 5

### Month Slicer (Left Panel)
Vertical list slicer (January–December) updating all visuals simultaneously.

### Mobile Model & Brand Slicers
Dropdown filters to isolate any specific model or brand across all visuals.

### Total Sales by City (Map Visual)
Interactive map plotting revenue across 19 cities including Mumbai, Delhi, Bangalore, Hyderabad, Chennai, Kolkata, Ludhiana, Jodhpur, and more.

### Total Quantity by Month (Line Chart)
Tracks monthly unit sales across the year:
- **Peak**: July — 1,700 units
- **Dip**: February — 1,451 units
- Indicates mid-year demand spikes useful for inventory planning.

### Brand Revenue Comparison (Bar Chart)
Apple leads at ₹162M, followed closely by Samsung (₹160M), OnePlus (₹154M), Vivo (₹150M), and Xiaomi (₹144M). Competitive landscape with no dominant brand.

### Customer Age Segmentation (Bar Chart)
- **45–59**: Highest revenue segment — ₹269M (35% share)
- **25–34**: Second largest — ₹191M
- Signals opportunity to target premium models toward the 45+ segment.

### Top 5 Mobile Models by Sales (Table)
| Model | Total Sales | Quantity | Transactions |
|-------|------------|----------|--------------|
| iPhone SE | ₹59.6M | 1,430 | 280 |
| OnePlus Nord | ₹57.9M | 1,409 | 273 |
| Galaxy Note 20 | ₹56.0M | 1,382 | 266 |
| Vivo Y51 | ₹54.8M | 1,429 | 283 |
| Galaxy S21 | ₹53.3M | 1,305 | 260 |

### Transactions by Payment Method (Bar Chart)
- UPI: 26.25%
- Credit Card: 25.89%
- Cash: 25.03%
- Debit Card: 22.83%

Near-equal distribution across all four channels — investment in all payment infrastructure is justified.

### Customer Ratings Distribution (Bar Chart)
- 5 stars: 311 | 4 stars: 185 | 3 stars: 137 | 2 stars: 119 | 1 star: 67
- Overall satisfaction is positive but the 119 two-star ratings warrant investigation.

### Total Sales by Day of Week (Bar Chart)
Saturday leads at ₹115M; Wednesday is lowest at ₹105M. Weekend peaks support scheduling of flash sales and campaigns.

---

## 💡 Business Impact & Insights

| Insight | Recommended Action |
|---------|-------------------|
| 💰 Apple & Samsung lead revenue but margins are similar across all 5 brands | Avoid over-investing in a single brand — diversified stock recommended |
| 👥 45–59 age group drives 35% of revenue | Target premium/flagship models toward this demographic |
| 📅 February dip (1,451 units) and July peak (1,700 units) | Plan promotional campaigns in Feb; ensure stock levels for July |
| 💳 Near-equal payment method split | Maintain and invest equally in UPI, card, and cash infrastructure |
| 📆 Saturday consistently outperforms weekdays | Schedule weekend-specific flash sales and offers |
| ⭐ 119 two-star ratings (12% of reviews) | Investigate — likely driven by specific models or cities |

---

## 📸 Dashboard Preview

![Mobile Sales Dashboard](https://github.com/harshvgupta98/POWERBI_Motorola_Sales_Dashboard/blob/main/Snapshot%20of%20Mobile%20Sales%20Dashboard.png)

---

## 📁 File Structure

```
mobile-sales-dashboard/
├── Motorola_Sales_Dashboard.pbit        # Power BI Template file
├── Mobile_Sales_Data.xlsx               # Source dataset (3,835 transactions)
├── Mobile_Sales_Dashboard.xlsx   # Supplementary Excel analysis workbook
├── Snapshot_of_Motorola_Sales_Dashboard.png  # Dashboard preview
└── README.md
```

---

## 🛠️ How to Use

1. Download `Motorola_Sales_Dashboard.pbit` and `Mobile_Sales_Data.xlsx`
2. Open the `.pbit` file in Power BI Desktop
3. When prompted, point to `Mobile_Sales_Data.xlsx` as the data source
4. Navigate the dashboard using the **Month slicer** and **Mobile Model dropdown**
5. Use the **map visual** to drill into specific cities
6. Open `Mobile_Sales_Dashboard.xlsx` for a detailed tabular breakdown by brand, city, age group, and day of week

> ⚠️ The `.pbit` file is a Power BI Template — it does not contain data itself. You must connect it to `Mobile_Sales_Data.xlsx` on first open.

---

## 💡 Key Power BI / DAX Concepts Used

| Concept | Applied In |
|---------|-----------|
| `SUMX` row-by-row iteration | Total Sales measure (price × units per row) |
| `COUNTROWS` | Transactions count measure |
| `PREVIOUSMONTH` time intelligence | Month-over-month sales comparison |
| `DIVIDE` with safe division | MoM % change without divide-by-zero errors |
| Auto date table relationships | Monthly and day-of-week time intelligence |
| Map visual with geocoding | City-level geographic distribution |
| Slicers (list + dropdown) | Month and model interactive filtering |
| Formatted KPI cards | At-a-glance summary metrics |
| Bar charts for categorical data | Brand, model, payment, day comparisons |
| Line chart for time series | Monthly quantity trend |
