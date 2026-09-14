# Retail Sales & Customer Analytics: A Multi-Year Analysis of Sales Trends, Customer Loyalty, Product & Regional Performance




---

##  Overview

This project analyzes **4 years of retail sales data** to uncover monthly and
yearly sales trends, identify high-value and churning customers, evaluate
product-line performance, and compare regional sales.

The goal is to help a retail business make **data-driven decisions** on
customer retention, product strategy, and regional focus.

**Dataset:** Public retail sales dataset containing customer purchases across
multiple product categories, regions, states, and cities.



---

###  Data Structure & Initial Checks

The database structure consists of a single fact table, `sales_data`, which contains transaction-level details for sales, customers, products, and regions with a total row count of 9800 records.



#### 🗂️ `sales_data`

| Column | Type |
| :--- | :--- |
| `row_id` | integer |
| `order_id` | character varying(50) |
| `order_date` | date |
| `ship_date` | date |
| `ship_mode` | character varying(50) |
| `customer_id` | character varying(50) |
| `customer_name` | character varying(100) |
| `segment` | character varying(50) |
| `country` | character varying(50) |
| `city` | character varying(100) |
| `state` | character varying(100) |
| `postal_code` | character varying(20) |
| `region` | character varying(50) |
| `product_id` | character varying(50) |
| `category` | character varying(50) |
| `sub_category` | character varying(50) |
| `product_name` | character varying(500) |
| `sales` | numeric(10,2) |

Prior to the beginning the analysis, a variety of checks were conducted for quality control and familiarization with the datasets. The SQL queries utilized to inspect and perform quality checks can be found here

#### 🔗 Relationships

*As this is a single flat table, there are no foreign key relationships to other tables. The `sales_data` table acts as a denormalized fact table containing both measures (e.g., `sales`) and descriptive dimension attributes (e.g., `customer_name`, `product_name`, `region`).*

##  Business Objectives

1. **Yearly & Monthly Sales Analysis** — Track performance across months,
   quarters, and years to identify peak and low periods.
2. **Customer Loyalty & Segmentation** — Classify customers as *new, active,*
   or *churned* and identify high-value vs. low-value segments.
3. **Product Performance** — Determine which products to expand, maintain,
   rebrand, or discontinue.
4. **Regional Comparison** — Compare state and regional sales to find
   consistent, declining, and inconsistent markets.

---

##  Tools & Technologies

| Category | Tools |
|---|---|
| Data Cleaning & Handling | Excel |
| Query & Extraction | SQL |
| Analysis & Visualization | Power BI |


---

##  Project Structure
