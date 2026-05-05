# 📱 Motorola Sales Dashboard

A dynamic, interactive Power BI dashboard built to analyse Motorola mobile sales performance across cities, models, payment methods, and time periods across India.

---

## 📌 Short Description / Purpose

The **Motorola Sales Dashboard** is a visually engaging Power BI report designed to help sales teams and business leaders monitor mobile sales performance across Indian cities. The dashboard tracks total sales, quantity, transactions, and customer ratings — enabling data-driven decisions around product strategy, regional focus, and payment trends.

---

## 🛠️ Tech Stack

The dashboard was built using the following tools and technologies:

- **📊 Power BI Desktop** – Main data visualization platform used for report creation.
- **📂 Power Query** – Data transformation and cleaning layer for preparing the sales data.
- **🧠 DAX (Data Analysis Expressions)** – Used for calculated measures such as `Total Sales`, `Total Quantity`, `Transactions`, and `Average`.
- **🗺️ Power BI Map Visual** – Used to plot Total Sales by City across India (powered by TomTom / OpenStreetMap).
- **📝 Data Modeling** – Single flat fact table (`Sales_Data`) with an auto-generated date table relationship for time intelligence.
- **📁 File Format** – `.pbit` (Power BI Template) for portability and `.png` for dashboard preview.

---

## 🧮 DAX Measures

| Measure | Expression | Description |
|---------|------------|-------------|
| `Total Sales` | `SUMX(Sales_Data, Sales_Data[Price Per Unit] * Sales_Data[Units Sold])` | Total revenue calculated as price × units for each row |
| `Total Quantity` | `SUM(Sales_Data[Units Sold])` | Total units sold across all transactions |
| `Transactions` | `COUNTROWS(Sales_Data)` | Total number of sales transactions |
| `Average` | `AVERAGE(Sales_Data[Price Per Unit])` | Average price per unit across all models |

---

## 📂 Data Source

**Source**: Motorola mobile sales transactional dataset covering Indian cities.

Data covering **4K transactions** across **19K units sold**, generating **₹769M in total sales**. The dataset is a single flat fact table (`Sales_Data`) containing transaction-level records with customer, product, location, and payment details.

---

## 📖 Data Dictionary

### Sales_Data (Fact Table)

| Column | Type | Description |
|--------|------|-------------|
| `Transaction ID` | Int | Unique identifier for each sales transaction |
| `Date` | DateTime | Date of the transaction |
| `Day Name` | String | Day of the week (e.g. Monday, Saturday) |
| `Brand` | String | Mobile brand name (e.g. Motorola, Samsung, Apple) |
| `Mobile Model` | String | Specific model name (e.g. Galaxy Note 20, iPhone SE) |
| `Units Sold` | Int | Number of units sold in the transaction |
| `Price Per Unit` | Decimal | Selling price per unit in local currency |
| `Customer Name` | String | Name of the customer |
| `Customer Age` | Int | Age of the customer in years |
| `City` | String | Indian city where the sale took place |
| `Payment Method` | String | Payment method used — UPI, Debit Card, Credit Card, Cash |
| `Customer Ratings` | Int | Customer satisfaction rating (1=Lowest, 5=Highest) |

### Date Table (Auto-generated)

| Column | Type | Description |
|--------|------|-------------|
| `Date` | DateTime | Full date value |
| `Year` | Int | Calendar year |
| `MonthNo` | Int | Month number (1–12) |
| `Month` | String | Month name (e.g. January) |
| `QuarterNo` | Int | Quarter number (1–4) |
| `Quarter` | String | Quarter label (e.g. Q1) |
| `Day` | Int | Day of the month |

---

## ✨ Features / Highlights

### 🔴 Business Problem

Sales teams and regional managers often struggle to identify:

- Which cities and mobile models are driving the most revenue?
- Are there seasonal trends in monthly quantity sold?
- Which payment methods are most preferred by customers?
- How do customer ratings vary and what does satisfaction look like overall?

…these questions are difficult to answer quickly from raw transactional data.

---

### 🎯 Goal of the Dashboard

To deliver an interactive visual tool that:

- Gives sales leadership a real-time view of total sales, quantity, and transactions at a glance.
- Enables regional analysis through an interactive map of sales by city across India.
- Supports product and inventory decisions by highlighting top-performing mobile models.
- Helps understand customer satisfaction trends through ratings distribution.

---

### 🖼️ Walkthrough of Key Visuals

- **Key KPIs (Top Row)**
  - Total Sales: **₹769M**
  - Total Quantity: **19K units**
  - Transactions: **4K**
  - Average Price Per Unit: **₹40K**

- **Month Slicer (Left Panel)**
  An interactive filter allowing users to drill down by any month (January–December) — updating all visuals simultaneously.

- **Mobile Model Slicer (Top Right)**
  Dropdown filter to isolate performance of a specific mobile model across all visuals.

- **Total Sales by City (Map Visual)**
  An interactive map plotting sales volume across Indian cities including Mumbai, Delhi, Bangalore, Hyderabad, Chennai, Kolkata, and more.

- **Total Quantity by Month (Line Chart)**
  Tracks monthly unit sales across the year. Peak month is **July (1,700 units)** and the lowest is **February (1,451 units)**, indicating mid-year demand spikes.

- **Top 5 Mobile Models by Sales (Table)**
  Ranks the top 5 models by Total Sales, Quantity, and Transactions:
  - Galaxy Note 20: ₹56M | 1,382 units | 266 transactions
  - iPhone SE: ₹59.6M | 1,430 units | 280 transactions
  - OnePlus Nord: ₹57.9M | 1,409 units | 273 transactions
  - Galaxy S21: ₹53.3M | 1,305 units | 260 transactions
  - Vivo Y51: ₹54.8M | 1,429 units | 283 transactions

- **Transactions by Payment Method (Pie Chart)**
  Breaks down transactions by payment type:
  - UPI: **26.25%**
  - Credit Card: **25.89%**
  - Cash: **25.03%**
  - Debit Card: **22.83%**
  Payment methods are nearly evenly distributed, indicating no single dominant channel.

- **Customer Ratings (Bar Chart)**
  Distribution of customer satisfaction ratings:
  - 5 stars: **311** customers
  - 4 stars: **185**
  - 3 stars: **137**
  - 2 stars: **119**
  - 1 star: **67**
  Majority of customers (311) gave the highest rating, reflecting strong satisfaction.

- **Total Sales by Day Name (Area Chart)**
  Saturday leads with **₹115M** in sales, while Wednesday is the lowest at **₹105M** — weekends consistently outperform weekdays.

- **Total Sales by Mobile Model (Bar Chart)**
  iPhone SE leads at **₹60M**, followed by OnePlus Nord (**₹58M**) and Galaxy Note 20 (**₹56M**).

---

### 💡 Business Impact & Insights

- **📍 Regional Strategy**: The city map highlights high-performing urban centres, helping sales teams prioritise distribution and marketing spend geographically.
- **📅 Seasonal Planning**: The February dip (1,451 units) and July peak (1,700 units) can guide inventory planning and promotional campaign timing.
- **📱 Product Focus**: iPhone SE and OnePlus Nord consistently rank at the top by both revenue and volume — strong candidates for featured promotions.
- **💳 Payment Infrastructure**: Near-equal payment method distribution suggests investment in all four payment channels (UPI, cards, cash) is justified.
- **⭐ Customer Satisfaction**: With 311 five-star ratings and only 67 one-star ratings, overall satisfaction is healthy — but the 119 two-star ratings warrant further investigation.
- **📆 Weekend Peaks**: Saturday and Monday outperform mid-week days — a useful insight for scheduling flash sales or targeted campaigns.

---

## 📸 Dashboard Preview

![Motorola Sales Dashboard](https://github.com/harshvgupta98/POWERBI_Motorola_Sales_Dashboard/blob/main/Snapshot%20of%20Motorola%20Sales%20Dashboard.png)

---

## 📁 File Structure

```
Motorola_Sales_Dashboard/
├── Motorola_Sales_Dashboard.pbit   # Power BI Template file
├── Mobile_Sales_Data.xlsx          # Source dataset
├── Motorola_Sales_Dashboard.png    # Dashboard preview
└── README.md
```
