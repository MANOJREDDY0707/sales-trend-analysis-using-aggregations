# TASK_6-Sales-Trend-Analysis-Using-Aggregations
MySQL-based Sales Trend Analysis project with a sample e-commerce dataset (online_sales) and queries to calculate monthly revenue, order volume, and time-based trends. Includes scripts for dataset creation, sample inserts, and analysis-ready SQL queries.

# 📊 MySQL Sales Trend Analysis

This project demonstrates how to analyze **sales performance over time** using MySQL.  
It includes a **sample e-commerce dataset** (`online_sales`), SQL scripts to create and populate the table, and a set of queries to calculate **monthly revenue, order volume, and time trends**.

---

## 📂 Project Contents
- **Dataset Schema** – E-commerce sales table with fields for order, customer, product, sales amount, region, and channel.
- **Sample Data Inserts** – Ready-to-use example transactions (Jan–Jun 2024).
- **Analysis Queries** – MySQL queries for:
  - Monthly revenue & order volume
  - Year-specific performance
  - Date-range-based filtering
  - Readable month formatting (`YYYY-MM`)
  - Optional month-over-month % change (MySQL 8+)

---

## 🛠️ Tech Stack
- **Database:** MySQL 8+ (compatible with MySQL 5.7 for basic queries)
- **Tools:** MySQL Workbench, CLI, or any MySQL-compatible interface
- **Language:** SQL

---

## 📑 Dataset Description
The `online_sales` table contains transaction-level details for e-commerce orders, including:
- **order_id** – Unique order reference
- **order_date** – Purchase date and time
- **customer_id** & **product_id** – Entity references for analysis
- **quantity**, **unit_price**, **amount** – Sales metrics
- **country** & **channel** – Geographic and channel segmentation

This structure supports **time trend analysis**, **sales forecasting**, and **customer behavior insights**.

---

## 🚀 How to Use
1. **Create Database & Table**  
   Run the `create_table.sql` script to set up the `online_sales` table.
2. **Insert Sample Data**  
   Execute `sample_inserts.sql` to load test transactions.
3. **Run Analysis Queries**  
   Use the provided `analysis_queries.sql` to explore trends.

---

## 📈 Example Query
```sql
SELECT
    DATE_FORMAT(order_date, '%Y-%m') AS year_month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY year_month
ORDER BY year_month;
