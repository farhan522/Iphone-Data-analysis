# Iphone-Data-analysis
iPhone sales analysis using Snowflake SQL – calculated averages, filtered records, and ordered sales data to gain insights.
# 📱 iPhone Sales Data Analysis using Snowflake SQL

Welcome to my iPhone Sales Data Analysis project! This analysis was performed using **Snowflake**, focusing on exploring the data, calculating average sales, filtering specific data, and ordering it for insights.

---

## 🚀 Project Overview

In this project, I used **Snowflake SQL** to:
- Load and query iPhone sales data
- Calculate average sales values
- Sort data using `ORDER BY`
- Filter specific entries using `WHERE`
- Apply other common SQL operations

This mini-project helped strengthen my understanding of Snowflake's data handling and analytical capabilities.

---

## 🧰 Tools & Technologies
- **Snowflake**
- **SQL**


-- Calculate average sales
SELECT AVG(sales) AS avg_sales FROM iphone_sales;

-- Order by sales (descending)
SELECT * FROM iphone_sales ORDER BY sales DESC;

-- Highest and lowest sale values
SELECT MAX(sales) AS max_sale, MIN(sales) AS min_sale FROM iphone_sales;

-- Filter sales greater than average
SELECT * 
FROM iphone_sales 
WHERE sales > (SELECT AVG(sales) FROM iphone_sales);

-- Sales by month 
SELECT TO_CHAR(sale_date, 'YYYY-MM') AS sale_month, SUM(sales) AS monthly_sales
FROM iphone_sales
GROUP BY sale_month
ORDER BY sale_month;


