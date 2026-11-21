# Retail-Sales-Analysis-postgreSQL

## Project Overview

An end-to-end exploratory and descriptive data analysis of a retail transactions dataset conducted in PostgreSQL. Built around a single `retail_sales` table within the `Retail` database, this project covers the complete data analytics workflow: schema creation, data cleaning, querying ten business questions, and translating analytical outputs into actionable business recommendations.

---

## Objectives

* Data Preparation:** Build a clean, reliable dataset by identifying and removing incomplete (`NULL`) records and standardising categorical values.
* Category Performance:** Measure net revenue and order volume across product categories to identify core revenue drivers.
* Customer Profiling:** Analyse customer demographics (gender and age) and total spend to identify high-value customer segments and category reach.
* Seasonality & Trends:** Track monthly sales performance and rank months within each year to uncover seasonal peaks.
* Purchasing Rhythm:** Categorise transactions into Morning, Afternoon, and Evening shifts to understand peak buying hours.

---

## Tools & SQL Concepts Used

* Database & RDBMS:** PostgreSQL (`Retail` database)
* SQL Techniques Demonstrated:
  * DDL & DML:** `CREATE TABLE`, `DROP TABLE`, `DELETE`, `UPDATE`
  * Filtering & Logic:** `WHERE`, `AND`, `OR`, `CASE` expressions, half-open date ranges
  * Aggregations & Grouping:** `SUM()`, `AVG()`, `COUNT()`, `COUNT(DISTINCT)`, `ROUND()`, `GROUP BY`, `ORDER BY`, `LIMIT`
  * Advanced Querying:** Common Table Expressions (`CTE` / `WITH`), `RANK()` window function (`OVER (PARTITION BY ...)`), and `EXTRACT()` for date/time parsing

---

## Dataset Description

The dataset consists of individual retail transaction records loaded from a spreadsheet into the `retail_sales` table (`11` columns), where each row represents a single transaction identified by `transaction_id`.

---

### Conclusion

This project establishes a structured, repeatable SQL workflow in PostgreSQL—progressing from database schema design and data cleaning to ten targeted business queries. By pairing core SQL techniques (aggregations, CASE logic, CTEs, and window functions) with an actionable decision framework, the analysis provides a practical foundation for data-driven retail merchandising, marketing, and operational planning

---

## Author 

Rahul Maske

---

### Database Schema

```sql
DROP TABLE IF EXISTS retail_sales;
CREATE TABLE retail_sales
(
    transaction_id INT PRIMARY KEY,
    sale_date      DATE,
    sale_time      TIME,
    customer_id    INT,
    gender         VARCHAR(15),
    age            INT,
    category       VARCHAR(15),
    price_per_unit FLOAT,
    quantity       INT,
    cogs           FLOAT,
    total_sale     FLOAT
);

