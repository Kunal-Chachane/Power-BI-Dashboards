# 🍕 Pizza Sales Analysis Dashboard
---

# 📊 Dashboard Preview


![Dashboard Page 1](https://raw.githubusercontent.com/Kunal-Chachane/Power-BI-Dashboards/main/Pizza%20Sales/images/pizza_sales_dashboard_page1.png)

![Dashboard Page 2](https://raw.githubusercontent.com/Kunal-Chachane/Power-BI-Dashboards/main/Pizza%20Sales/images/pizza_sales_dashboard_page2.png)

---

# 📌 Project Overview

The **Pizza Sales Analysis Dashboard** is an end-to-end Business Intelligence project developed using **PostgreSQL, SQL, Power BI, Power Query, and DAX**.

This project analyzes pizza sales transactions to uncover revenue trends, customer ordering behavior, product performance, and operational insights. The dashboard transforms raw transactional data into actionable business insights that help stakeholders optimize sales strategies, inventory planning, and customer experience.

---

<p align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Analytics-blue?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Measures-orange?style=for-the-badge)

</p>

---

# 🎯 Business Objectives

- Analyze overall sales performance and revenue trends.
- Identify top-performing and underperforming pizzas.
- Understand customer purchasing behavior.
- Evaluate daily and monthly sales trends.
- Analyze pizza category and size preferences.
- Generate actionable business recommendations.
- Support data-driven decision-making.

---

# 🔄 Data Pipeline

### Data Collection
- Imported pizza sales dataset into PostgreSQL.
- Structured and validated transactional data.

### SQL Analysis
- Revenue Analysis
- Sales Trend Analysis
- Product Performance Analysis
- Customer Ordering Analysis
- KPI Calculation

### Data Transformation
- Connected PostgreSQL to Power BI.
- Cleaned and transformed data using Power Query.

### Dashboard Development
- Built relational data model.
- Developed DAX measures and KPIs.
- Designed interactive dashboards and visualizations.

---

# 🚀 Key Performance Indicators

| KPI | Value |
|------|--------|
| 💰 Total Revenue | ₹6.79 Crore |
| 📦 Total Orders | 21,350 |
| 🍕 Total Pizzas Sold | 49,574 |
| 💵 Average Order Value | ₹3,180 |
| 📈 Average Pizza Per Order | 2.32 |

---

# 📈 Dashboard Features

## 1️⃣ Sales Performance Overview

Tracks overall business performance through KPI monitoring.

### Metrics
- Total Revenue
- Total Orders
- Total Pizza Sold
- Average Order Value
- Average Pizza Per Order

### Insight
Generated approximately **₹6.79 Crore** in revenue from more than **21,000 customer orders**.

---

## 2️⃣ Daily Sales Analysis

Analyzes order volume across weekdays.

### Key Findings

| Day | Orders |
|------|---------|
| Friday | 8.1K |
| Saturday | 7.3K |
| Thursday | 7.1K |

### Insight

Customer demand peaks during weekends, especially on Fridays and Saturdays.

---

## 3️⃣ Monthly Sales Analysis

Tracks order volume throughout the year.

### Top Months

| Month | Orders |
|---------|---------|
| July | 1,935 |
| May | 1,853 |
| March | 1,840 |

### Insight

Sales remain stable throughout the year with seasonal peaks during mid-year months.

---

## 4️⃣ Pizza Category Analysis

| Category | Revenue |
|------------|----------|
| Classic | ₹1.83 Cr |
| Supreme | ₹1.73 Cr |
| Chicken | ₹1.63 Cr |
| Veggie | ₹1.61 Cr |

### Insight

Classic pizzas generated the highest revenue contribution among all categories.

---

## 5️⃣ Pizza Size Analysis

| Pizza Size | Revenue Contribution |
|------------|---------------------|
| Large | 45.89% |
| Medium | 30.49% |
| Regular | 21.77% |
| X-Large | 1.72% |
| XX-Large | 0.12% |

### Insight

Large pizzas generated nearly half of total revenue, indicating strong customer preference.

---

# 🏆 Best Performing Pizzas

## By Revenue

| Pizza | Revenue |
|---------|---------|
| Thai Chicken Pizza | ₹36.05 Lakh |
| Barbecue Chicken Pizza | ₹35.50 Lakh |
| California Chicken Pizza | ₹34.37 Lakh |

---

## By Quantity Sold

| Pizza | Quantity |
|---------|----------|
| Classic Deluxe Pizza | 2,453 |
| Barbecue Chicken Pizza | 2,432 |
| Hawaiian Pizza | 2,422 |

---

## By Orders

| Pizza | Orders |
|---------|---------|
| Classic Deluxe Pizza | 2,329 |
| Hawaiian Pizza | 2,283 |
| Pepperoni Pizza | 2,279 |

---

# 📉 Lowest Performing Pizzas

## By Revenue

| Pizza | Revenue |
|---------|---------|
| Brie Carre Pizza | ₹9.62 Lakh |
| Green Garden Pizza | ₹11.59 Lakh |
| Spinach Supreme Pizza | ₹12.68 Lakh |

---

## By Orders

| Pizza | Orders |
|---------|---------|
| Brie Carre Pizza | 480 |
| Mediterranean Pizza | 912 |
| Calabrese Pizza | 918 |

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

The project leveraged PostgreSQL to perform business analysis and KPI calculations.

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

### Best Selling Pizza

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

- Customers purchase an average of **2.32 pizzas per order**.
- Weekend demand significantly exceeds weekday demand.
- Large-sized pizzas dominate customer preferences.

### Revenue Insights

- Total revenue exceeded **₹6.79 Crore**.
- Classic pizzas generated the highest category revenue.
- Top-selling pizzas contributed significantly to total revenue.

### Operational Insights

- Inventory should prioritize high-demand pizzas.
- Additional staffing is recommended during weekends.
- Low-performing products may require promotional strategies or menu optimization.

---

# 🛠️ Tools & Technologies

| Category | Technology |
|------------|------------|
| Database | PostgreSQL |
| Query Language | SQL |
| BI Tool | Power BI |
| Data Transformation | Power Query |
| Calculations | DAX |
| Data Source | CSV |
| Visualization | Power BI |

---

# 💡 Skills Demonstrated

### SQL & Database
- PostgreSQL
- SQL Query Writing
- Aggregations
- KPI Analysis
- Business Reporting

### Data Analytics
- Data Cleaning
- Data Transformation
- Exploratory Data Analysis (EDA)
- KPI Development

### Power BI
- Dashboard Development
- Data Modeling
- DAX Calculations
- Power Query
- Interactive Reporting

### Business Intelligence
- Sales Analytics
- Product Performance Analysis
- Customer Behavior Analysis
- Executive Reporting

---

# 📂 Project Structure

```text
Pizza Sales/
│
├── images/
│   ├── pizza_sales_dashboard_page1.png
│   ├── pizza_sales_dashboard_page2.png
│   ├── Total Revenue.png
│   ├── Total Orders.png
│   ├── Total_pizza_sold.png
│   └── Total_orders_every_month.png
│
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

✅ Optimize inventory allocation

✅ Improve menu strategy

✅ Understand customer purchasing behavior

✅ Support data-driven business decisions

---

# 👨‍💻 Author

## Kunal Chachane

**Data Analyst | Power BI Developer**

🔗 LinkedIn: https://www.linkedin.com/in/kunal-chachane

🐙 GitHub: https://github.com/Kunal-Chachane

---

⭐ If you found this project useful, consider giving it a star!
