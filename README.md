# Retail Sales & Customer Analytics: A Multi-Year Analysis of Sales Trends, Customer Loyalty, Product & Regional Performance




---

##  Project Background

This project analyzes open-source retail sales data covering customer transactions across products, categories, and regions over a four-year period. By analyzing this data with technical tools, the project uncovers actionable insights across four key areas:


- **Yearly and Monthly Sales Analysis:** Examines sales performance across years, quarters, and months to identify growth trends, seasonal patterns, and key periods of strength or weakness.

- **Customer Loyalty Analysis:** Segments customers based on purchase behavior and value, while identifying new, active, loyal, and churned customers to support retention and customer development strategies.

- **Product Performance:** Evaluates product-level sales, order volume, and performance trends to identify high-performing products, products requiring attention, and opportunities for portfolio optimization.

- **Regional Comparison:** Compares sales performance across regions and states to identify strong, growing, declining, and variable markets and support decisions on where to maintain, strengthen, or reassess regional focus.

Together, these insights provide a business-focused view of **sales trends, customer behavior, product performance, and regional opportunities**, helping the business make more informed decisions around customer retention, product strategy, and regional priorities.




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



---

##  Tools & Technologies

| Category | Tools |
|---|---|
| Data Cleaning & Handling | Excel |
| Query & Extraction | SQL |
| Analysis & Visualization | Power BI |


---

##  Executive Summary
