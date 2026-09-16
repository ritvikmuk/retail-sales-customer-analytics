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
<h3 align="center">Sales Revenue Analysis (2015–2018)</h3>

<img width="1031" height="477" alt="Screenshot 2026-09-14 214544" src="https://github.com/user-attachments/assets/0c16ae84-2be0-4a69-86e0-9b1a99dd16d4" />

<table>
<tr>
<td width="50%" valign="top">

### 1. Revenue Growth and Highest Performance:

- **2018 recorded the highest annual sales of $722,052**, representing **20.3%** growth over 2017. November 2018 was also the highest-performing month across the four-year period, generating approximately **$117,938** in sales.

- Following the **4.3% decline in 2016**, sales recovered strongly in 2017, growing by **30.6%**, followed by a further **20.3%** increase in 2018.

- The results indicate a strong recovery after the 2016 downturn, with **two consecutive years of positive annual growth.**

### 2. Declining Trend:

- **2016 was the weakest-performing year**, with sales of approximately **$459,436**, representing a **4.3%** decline from 2015.

- Compared with 2015, **Q1 and Q3 declined in 2016**, while Q2 and Q4 improved.

- Months such as **March, June, and September** each declined by more than **$10,000** compared with 2015. Factors such as **market changes, competitor actions, or supply chain issues** should be investigated.

</td>

<td width="50%" valign="top">

### 3. Quarterly Trends and Seasonal Patterns:

- **Q4 was the strongest-performing quarter in each year**, indicating a recurring concentration of sales toward the end of the year.

- **September was also a consistently strong month**, at times approaching the sales levels of individual Q4 months.

- **Q1 generally recorded the weakest quarterly performance**, with January and February frequently appearing among the lower-performing months.

- The recurring **Q4 strength and Q1 weakness** suggest that seasonal patterns should be considered when planning **inventory, staffing, and promotional activity.**

### 4. Recommendations and Key Takeaways:

- Investigate the **2016 downturn** by examining factors such as **market changes, competitor actions, supply chain issues, and other operational or market indicators** where available.

- Since **Q4 performed strongly in every year**, maintain this momentum through focused marketing and sales strategies while ensuring **inventory and staffing are optimized** to handle higher demand.

- Address **Q1 weakness** through targeted testing, such as **early-year promotions, product bundles, or customer reactivation campaigns**, while monitoring whether these initiatives improve sales without unnecessarily reducing margins.

</td>
</tr>
</table>

##  Key Insights And Analysis
<h3 align="center">Sales Trends Analysis </h3>

<img width="1147" height="372" alt="Screenshot 2026-09-15 215022" src="https://github.com/user-attachments/assets/80e433ee-3781-4f41-9e8f-cf8010e4baca" />


### Sales Revenue 

- **2016 – Decline:** Sales declined **4.25% YoY**, driven mainly by weaker **Q1 (-16%) and Q3 (-10%)**. Although Q2 and Q4 grew 2%, the overall year remained below 2015. February grew **164% YoY** but still recorded the year's lowest sales (**$11,951**), while November was the highest (**$75,249**).
- **2017 – Strong recovery:** Sales grew **30.8%**, the highest annual growth across the period. Q1 and Q2 were 50% higher than 2016, with **December recording the highest monthly sales ($95,739)**.
- **2018 – Continued growth:** Sales increased **20.3% YoY**, reaching the **highest annual revenue** in the four-year period along with November month being the **highest revenue generating month** among four year period. Q1, Q3 and Q4 grew, while Q2 declined **5.6%**. January and August recorded **100%+ YoY growth**, while weaker performance in February, May and December contributed to the quarterly variation.

### Average Order Value (AOV)

- **2015:** Recorded the highest annual AOV at **$506.71**.
- **2016:** AOV declined approximately **11%**, with every quarter below its 2015 counterpart, indicating lower revenue generated per order.
- **2017:** AOV recovered **3%**, supported by stronger Q1 (**$520.71**) and Q4 (**$512.89**), although Q3 fell sharply to **$373.13**.
- **2018:** AOV declined another **6%** to **$434.71**, with Q2 recording the lowest quarterly AOV across the period (**$354.33**).

**Quarterly pattern**:
| Quarter | Pattern | AOV Range |
|---|---|---|
| Q1 | Premium quarter | $582 – $518 |
| Q2 | Weakest, declining | $440 – $354 |
| Q3 | Declining (growth in 2018) | $542 – $441 |
| Q4 | Strong, moderately volatile | $490 – $445 |

### Order Volume

- **Order volume increased consistently over the four years**, with each year generally recording more orders than the previous year across comparable quarters.
- Growth accelerated in the later years, with **2017 adding 276 orders** over 2016 and **2018 adding a further 366 orders** over 2017.

<h3 align="center">Product Performance</h3>

<img width="973" height="485" alt="Screenshot 2026-09-17 022334" src="https://github.com/user-attachments/assets/e4e53b16-4326-47f2-a2ac-c85353fdb7b1" />





