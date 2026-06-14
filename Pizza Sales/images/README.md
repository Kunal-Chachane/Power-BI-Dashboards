# 🍕 Pizza Sales Analysis Dashboard

<p align="center">
  <img src="./Pizza Sales Dashboard Page1.png" alt="Pizza Sales Dashboard" width="100%">
  <img src="./Pizza Sales Dashboard Page1.png" alt="Pizza Sales Dashboard" width="100%">
</p>

<p align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge\&logo=powerbi\&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge\&logo=postgresql\&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analytics-blue?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Measures-orange?style=for-the-badge)

</p>

---

# 📌 Project Overview

The **Pizza Sales Analysis Dashboard** is an end-to-end Business Intelligence project developed using **PostgreSQL, SQL, Power BI, Power Query, and DAX**.

This project analyzes pizza sales transactions to uncover revenue trends, customer ordering patterns, product performance, and operational insights. The dashboard enables stakeholders to monitor KPIs, identify top-selling products, and make data-driven business decisions.

---

# 🎯 Business Objectives

* Analyze overall sales performance and revenue trends.
* Identify best-selling and low-performing pizzas.
* Understand customer purchasing behavior.
* Evaluate daily and monthly sales trends.
* Analyze pizza category and size preferences.
* Generate actionable business insights.
* Support inventory and marketing decisions.

---

# 🔄 Data Pipeline

### 1. Data Collection

* Imported raw pizza sales data into PostgreSQL.
* Created structured tables for analysis.

### 2. SQL Analysis

* Performed analytical queries using PostgreSQL.
* Calculated KPIs and sales metrics.
* Identified top and bottom-performing products.

### 3. Data Transformation

* Connected PostgreSQL to Power BI.
* Cleaned and transformed data using Power Query.

### 4. Dashboard Development

* Built data model and relationships.
* Created DAX measures and KPIs.
* Designed interactive visualizations and reports.

---

# 📊 Dashboard Preview

## Executive Dashboard

![Executive Dashboard](./Pizza%20Sales%20Dashboard%20Page1.png)

---

## Product Performance Dashboard

![Product Performance Dashboard](./Pizza%20Sales%20Dashboard%20page2.png)

---

# 🚀 Key Performance Indicators

| KPI                        | Value       |
| -------------------------- | ----------- |
| 💰 Total Revenue           | ₹6.79 Crore |
| 📦 Total Orders            | 21,350      |
| 🍕 Total Pizzas Sold       | 49,574      |
| 💵 Average Order Value     | ₹3,180      |
| 📈 Average Pizza Per Order | 2.32        |

> Revenue converted approximately from dashboard values into Indian Rupees (₹).

---

# 📈 Dashboard Features

## Sales Performance Analysis

Tracks overall business performance through:

* Total Revenue
* Total Orders
* Total Pizza Sold
* Average Order Value
* Average Pizzas per Order

### Key Insight

The business generated approximately **₹6.79 Crore** from over **21,000 customer orders**.

---

## Daily Sales Analysis

Analyzes order volume by weekday.

### Key Findings

* Friday recorded the highest order volume.
* Weekend sales significantly outperformed weekdays.
* Customer demand peaks during weekends.

---

## Monthly Trend Analysis

Tracks sales trends across all months.

### Key Findings

* July generated the highest number of orders.
* January and May also showed strong sales performance.
* Seasonal fluctuations are visible throughout the year.

---

## Pizza Category Analysis

### Revenue Contribution

| Category | Revenue Share |
| -------- | ------------- |
| Classic  | 26.91%        |
| Supreme  | 25.46%        |
| Chicken  | 23.96%        |
| Veggie   | 23.68%        |

### Key Insight

The **Classic Pizza Category** generated the highest revenue contribution.

---

## Pizza Size Analysis

### Revenue Contribution

| Size     | Revenue Share |
| -------- | ------------- |
| Large    | 45.89%        |
| Medium   | 30.49%        |
| Regular  | 21.77%        |
| X-Large  | 1.72%         |
| XX-Large | 0.12%         |

### Key Insight

Large pizzas accounted for nearly **46% of total revenue**, making them the most preferred size.

---

# 🏆 Best Performing Pizzas

## By Revenue

| Pizza                    | Revenue     |
| ------------------------ | ----------- |
| Thai Chicken Pizza       | ₹36.05 Lakh |
| Barbecue Chicken Pizza   | ₹35.50 Lakh |
| California Chicken Pizza | ₹34.37 Lakh |

---

## By Quantity Sold

| Pizza                  | Quantity |
| ---------------------- | -------- |
| Classic Deluxe Pizza   | 2,453    |
| Barbecue Chicken Pizza | 2,432    |
| Hawaiian Pizza         | 2,422    |

---

## By Orders

| Pizza                | Orders |
| -------------------- | ------ |
| Classic Deluxe Pizza | 2,329  |
| Hawaiian Pizza       | 2,283  |
| Pepperoni Pizza      | 2,279  |

---

# 📉 Lowest Performing Pizzas

## By Revenue

| Pizza                 | Revenue     |
| --------------------- | ----------- |
| Brie Carre Pizza      | ₹9.62 Lakh  |
| Green Garden Pizza    | ₹11.59 Lakh |
| Spinach Supreme Pizza | ₹12.68 Lakh |

---

## By Quantity Sold

| Pizza               | Quantity |
| ------------------- | -------- |
| Brie Carre Pizza    | 490      |
| Mediterranean Pizza | 934      |
| Calabrese Pizza     | 937      |

---

## By Orders

| Pizza               | Orders |
| ------------------- | ------ |
| Brie Carre Pizza    | 480    |
| Mediterranean Pizza | 912    |
| Calabrese Pizza     | 918    |

---

# 📸 KPI Snapshots

## 💰 Total Revenue

![Total Revenue](./images/Total%20Revenue.png)

---

## 📦 Total Orders

![Total Orders](./images/Total%20Orders.png)

---

## 🍕 Total Pizza Sold

![Total Pizza Sold](./images/Total_pizza_sold.png)

---

## 📅 Monthly Orders Trend

![Monthly Orders](./images/Total_orders_every_month.png)

---

# 🗄️ PostgreSQL Analysis

The project utilized PostgreSQL for data exploration and business analysis.

### Total Revenue

```sql
SELECT
    ROUND(SUM(total_price),2) AS total_revenue
FROM pizza_sales;
```

### Total Orders

```sql
SELECT
    COUNT(DISTINCT order_id) AS total_orders
FROM pizza_sales;
```

### Top Selling Pizza

```sql
SELECT
    pizza_name,
    SUM(quantity) AS total_quantity
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_quantity DESC
LIMIT 5;
```

### Revenue by Category

```sql
SELECT
    pizza_category,
    ROUND(SUM(total_price),2) AS revenue
FROM pizza_sales
GROUP BY pizza_category
ORDER BY revenue DESC;
```

---

# 🧮 DAX Measures

### Total Revenue

```DAX
Total Revenue =
SUM(PizzaSales[total_price])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(PizzaSales[order_id])
```

### Total Pizza Sold

```DAX
Total Pizza Sold =
SUM(PizzaSales[quantity])
```

### Average Order Value

```DAX
Avg Order Value =
DIVIDE([Total Revenue],[Total Orders])
```

### Average Pizza Per Order

```DAX
Avg Pizza Per Order =
DIVIDE([Total Pizza Sold],[Total Orders])
```

---

# 🔍 Key Business Insights

### Customer Insights

* Customers purchase an average of **2.32 pizzas per order**.
* Weekend demand is significantly higher than weekdays.
* Large-sized pizzas dominate customer preferences.

### Revenue Insights

* Total revenue exceeded **₹6.79 Crore**.
* Classic pizzas generated the highest category revenue.
* Top-selling pizzas contributed significantly to overall sales.

### Operational Insights

* Inventory should prioritize top-selling pizzas.
* Weekend staffing should be increased.
* Underperforming pizzas may require menu optimization.

---

# 🛠️ Tools & Technologies

| Category            | Technology  |
| ------------------- | ----------- |
| Database            | PostgreSQL  |
| Query Language      | SQL         |
| BI Tool             | Power BI    |
| Data Transformation | Power Query |
| Calculations        | DAX         |
| Data Source         | CSV         |
| Visualization       | Power BI    |

---

# 💡 Skills Demonstrated

### SQL & Database

* PostgreSQL
* SQL Query Writing
* Aggregations
* Business Analysis Queries
* Data Extraction

### Data Analytics

* Data Cleaning
* Data Transformation
* Exploratory Data Analysis (EDA)
* KPI Development

### Power BI

* Data Modeling
* DAX Calculations
* Dashboard Development
* Interactive Reporting
* Data Visualization

### Business Intelligence

* Sales Analytics
* Product Performance Analysis
* Customer Behavior Analysis
* Executive Reporting

---

# 📂 Project Structure

```text
Pizza Sales/
│
├── images/
│   ├── Total Orders.png
│   ├── Total Revenue.png
│   ├── Total_orders_every_month.png
│   └── Total_pizza_sold.png
│
├── Pizza Sales Dashboard Page1.png
├── Pizza Sales Dashboard page2.png
├── Pizza_sales_dashboard.pbix
├── Pizza_sales_dashboard.pdf
├── pizza_sales_excel_file.csv
│
└── README.md
```

---

# 📌 Business Impact

This dashboard enables stakeholders to:

✅ Monitor sales performance in real-time

✅ Identify top-performing products

✅ Optimize inventory allocation

✅ Improve menu strategy

✅ Understand customer purchasing behavior

✅ Support data-driven business decisions

---

# 👨‍💻 Author

### Kunal Chachane

**Data Analyst | Power BI Developer**

🔗 LinkedIn: https://www.linkedin.com/in/kunal-chachane

🐙 GitHub: https://github.com/Kunal-Chachane

---

⭐ If you found this project valuable, consider giving it a star!
