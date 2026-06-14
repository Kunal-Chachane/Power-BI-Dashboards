# 🍕 Pizza Sales Analysis Dashboard

<p align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge\&logo=powerbi\&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge\&logo=postgresql\&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analytics-blue?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Measures-orange?style=for-the-badge)

</p>

---

# 📌 Project Overview

The Pizza Sales Analysis Dashboard is an end-to-end Business Intelligence solution developed using **PostgreSQL, SQL, Power BI, Power Query, and DAX**.

This project analyzes pizza sales transactions to uncover revenue trends, customer ordering behavior, product performance, and operational insights. The dashboard provides stakeholders with actionable insights for improving sales performance, inventory planning, and business decision-making.

---

# 🎯 Business Objectives

* Analyze overall sales performance and revenue trends.
* Identify top-performing and underperforming pizzas.
* Understand customer ordering behavior.
* Evaluate daily and monthly sales patterns.
* Analyze pizza category and size preferences.
* Support business decisions with data-driven insights.

---

# 🔄 Data Pipeline

### Database Layer

* Imported pizza sales data into PostgreSQL.
* Structured data for analytical querying.

### SQL Analysis

* Revenue Analysis
* Sales Trend Analysis
* Product Performance Analysis
* Customer Ordering Analysis
* KPI Calculation

### Data Transformation

* Connected PostgreSQL with Power BI.
* Performed cleaning and transformation using Power Query.

### Dashboard Development

* Created data model.
* Developed DAX measures.
* Designed interactive dashboards.

---

# 📊 Dashboard Preview

## Executive Dashboard

![Dashboard](./Pizza%20Sales%20Dashboard%20Page1.png)

---

## Product Performance Dashboard

![Dashboard 2](./Pizza%20Sales%20Dashboard%20page2.png)

---

# 🚀 Key Performance Indicators

| KPI                        | Value       |
| -------------------------- | ----------- |
| 💰 Total Revenue           | ₹6.79 Crore |
| 📦 Total Orders            | 21,350      |
| 🍕 Total Pizzas Sold       | 49,574      |
| 💵 Average Order Value     | ₹3,180      |
| 📈 Average Pizza Per Order | 2.32        |

---

# 📈 Dashboard Features

## Sales Performance Analysis

Tracks business performance using:

* Total Revenue
* Total Orders
* Total Pizza Sold
* Average Order Value
* Average Pizza Per Order

### Insight

Generated approximately **₹6.79 Crore** in revenue from more than **21,000 customer orders**.

---

## Daily Order Analysis

### Key Findings

* Friday recorded the highest sales volume.
* Weekend demand significantly outperformed weekdays.
* Peak ordering activity occurred during weekends.

---

## Monthly Sales Analysis

### Key Findings

* July generated the highest order volume.
* January and May also recorded strong sales performance.
* Seasonal fluctuations can be observed throughout the year.

---

## Pizza Category Analysis

| Category | Revenue Contribution |
| -------- | -------------------- |
| Classic  | 26.91%               |
| Supreme  | 25.46%               |
| Chicken  | 23.96%               |
| Veggie   | 23.68%               |

### Insight

Classic pizzas contributed the highest revenue share.

---

## Pizza Size Analysis

| Size     | Revenue Contribution |
| -------- | -------------------- |
| Large    | 45.89%               |
| Medium   | 30.49%               |
| Regular  | 21.77%               |
| X-Large  | 1.72%                |
| XX-Large | 0.12%                |

### Insight

Large pizzas generated nearly half of the total revenue.

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

## By Total Orders

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

## By Orders

| Pizza               | Orders |
| ------------------- | ------ |
| Brie Carre Pizza    | 480    |
| Mediterranean Pizza | 912    |
| Calabrese Pizza     | 918    |

---

# 📸 KPI Snapshots

## 💰 Total Revenue

![Revenue](./images/Total%20Revenue.png)

---

## 📦 Total Orders

![Orders](./images/Total%20Orders.png)

---

## 🍕 Total Pizzas Sold

![Pizzas Sold](./images/Total_pizza_sold.png)

---

## 📅 Monthly Orders Trend

![Monthly Orders](./images/Total_orders_every_month.png)

---

# 🗄️ PostgreSQL Analysis

The project utilized PostgreSQL to perform business analysis and KPI calculations.

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

### Customer Behavior

* Customers purchase an average of **2.32 pizzas per order**.
* Weekend demand significantly exceeds weekday demand.
* Large-sized pizzas are the most preferred option.

### Revenue Insights

* Total revenue exceeded **₹6.79 Crore**.
* Classic category generated the highest revenue contribution.
* Top-selling pizzas account for a substantial share of overall sales.

### Operational Insights

* Inventory should prioritize high-demand pizza categories.
* Weekend staffing should be increased to meet customer demand.
* Underperforming products require promotional strategies or menu optimization.

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
* Data Extraction
* Business Analysis

### Data Analytics

* Data Cleaning
* Data Transformation
* Exploratory Data Analysis (EDA)
* KPI Development

### Power BI

* Data Modeling
* Dashboard Development
* DAX Calculations
* Power Query
* Interactive Reporting

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
│   ├── Total Revenue.png
│   ├── Total Orders.png
│   ├── Total_pizza_sold.png
│   └── Total_orders_every_month.png
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

✅ Monitor sales performance in real time

✅ Identify top-performing products

✅ Optimize inventory planning

✅ Improve menu strategy

✅ Understand customer ordering behavior

✅ Support data-driven decision-making

---

# 👨‍💻 Author

## Kunal Chachane

**Data Analyst | Power BI Developer**

🔗 LinkedIn: https://www.linkedin.com/in/kunal-chachane

🐙 GitHub: https://github.com/Kunal-Chachane

---

⭐ If you found this project useful, consider giving it a sta
