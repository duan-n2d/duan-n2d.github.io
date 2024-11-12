---
title: 'Top SQL commands I frequently use'
date: 2024-11-07
permalink: /posts/2024/11/sql-syntax/
tags:
  - work
  - data
---

# Top SQL commands I frequently use
As a data analyst, SQL is an essential tool in my daily workflow. Throughout my projects in data analysis, I've found certain SQL commands to be incredibly powerful and versatile. Here are the top SQL commands I frequently use:

1. SELECT and WHERE Clauses

``` sql
SELECT column1, column2
FROM table_name
WHERE condition;
```
This is the bread and butter of data retrieval. I use this to filter and extract specific data points in projects like my Adventure Works Cycles sales analysis.

2. JOIN Operations
```sql
SELECT t1.column1, t2.column2
FROM table1 t1
INNER JOIN table2 t2 ON t1.key = t2.key;
```
Joining tables is crucial for combining data from multiple sources. In my Azure Data Engineering projects, this has been instrumental in creating comprehensive datasets.

3. GROUP BY and Aggregate Functions
```sql
SELECT category, 
       COUNT(*) as total_count, 
       AVG(sales) as average_sales
FROM sales_table
GROUP BY category;
```
Essential for customer segmentation and analysis, as demonstrated in my RFM (Recency, Frequency, Monetary) customer segmentation project.

4. Window Functions
```sql
SELECT 
    customer_id,
    sales_amount,
    ROW_NUMBER() OVER (PARTITION BY category ORDER BY sales_amount DESC) as sales_rank
FROM sales_data;
```
Powerful for ranking and creating more complex analytical queries, especially useful in my food delivery profitability analysis.

5. Subqueries
```sql
SELECT *
FROM customers
WHERE customer_id IN (
    SELECT customer_id 
    FROM orders 
    WHERE order_date > '2024-01-01'
);
```
Allows for more complex data filtering and analysis, which I've used extensively in my business intelligence solutions.

6. CTEs
```sql
WITH customer_sales AS (
    SELECT 
        customer_id,
        SUM(total_amount) AS total_sales
    FROM sales
    GROUP BY customer_id
)
SELECT 
    c.customer_name,
    cs.total_sales
FROM customers c
JOIN customer_sales cs ON c.customer_id = cs.customer_id;
```
CTEs are temporary named result sets created within a SELECT, INSERT, UPDATE, DELETE, or MERGE statement. They help break down complex queries into more digestible, logical parts.