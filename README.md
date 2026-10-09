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
<br><br><br>

<h2 align="center">Sales Trends Analysis </h2>

<img width="1147" height="372" alt="Screenshot 2026-09-15 215022" src="https://github.com/user-attachments/assets/80e433ee-3781-4f41-9e8f-cf8010e4baca" />


### Sales Revenue 


| Year | Total Sales | Annual YoY % | Q1 YoY % | Q2 YoY % | Q3 YoY % | Q4 YoY % |
|------|-------------|--------------|----------|----------|----------|----------|
| 2015 | 479,856.27  | -            | -        | -        | -        | -        |
| 2016 | 459,435.94  | -4.3%        | -15.7%   | +2.1%    | -9.8%    | +1.8%    |
| 2017 | 600,192.80  | +30.6%       | +48.6%   | +54.0%   | +7.4%    | +29.6%   |
| 2018 | 722,051.96  | +20.3%       | +31.9%   | -5.6%    | +40.4%   | +18.8%   |

> **Note:** Quarterly YoY % shows the change vs. the same quarter in the prior year (e.g., Q1 2017 = Q1 2017 vs. Q1 2016). 2015 has no prior-year data

- **2015 → 2016**: **Decline (-4.25%)**. Sales fell as weaker Q1 (-16%) and Q3 (-10%) outweighed 2% growth in Q2 and Q4. The drop comes down to two months, March (-22K) and September (-19K, an unusually high 2015 base). February grew 164% but from a tiny base and was still the year's lowest month ($11,951), while November was the 2016 peak ($75,249).

- **2016 → 2017**: **Strong recovery (+30.6%)**. This was the highest growth of the period and was front-loaded, with Q1 and Q2 each 50% above 2016. Four months drove about two-thirds of the gain: October (+29K), May (+27K), December (+21K) and March (+18K). May 2017 looks like a one-off spike rather than a trend, and December was the year's peak ($95,739).

- **2017 → 2018**: **Continued growth (+20.3%)**. Revenue hit its highest annual level of the period, with Q2 (-5.6%) the only quarterly decline. The top contributors were November (+39K, the highest month across all four years), January and August recorded **100%+ YoY growth**. The Q2 dip came from April (-9%) and May (-23%, exaggerated by the strong May 2017), partly offset by June (+20%). February and December each fell ~13%, and December dropped after November's peak, unlike in 2017.

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

<br><br><br>

<h2 align="center">Product Performance</h2>

<img width="992" height="556" alt="Screenshot 2026-09-23 004123" src="https://github.com/user-attachments/assets/de1a1a60-930f-4682-bafc-5cc1ee05b08b" />



<table>
<tr>
<td width="33.3%" valign="top">



### Product Performance
- Canon imageCLASS 2200 Advanced Copier leads all products with $61,599.82 in total sales, despite a modest order count of just 5
- Fellowes PB500 Electric Punch and Cisco TelePresence System EX90 round out the top 3, but tell very different stories — Fellowes drives revenue through volume (10 orders), while Cisco does it through one high-value transaction ($22,638.48 in a single order)
- On the other end, Eureka Disposable Bags is the weakest performer, closing out the ranking with the lowest sales overall


</td>

<td width="33.3%" valign="top">

### Average Order Value (AOV)
***Note**: While the Power BI report highlights the top 10 AOV products overall, this yearly trend view adds deeper analysis — showing how these products' AOV changed over time.*
- AOV overall shows a general declining trend from 2015 through 2018 across the top 10 products — though this pattern isn't uniform across every product (e.g., HP LaserJet does not follow the same decline) and some products — Cisco TelePresence, Canon imageCLASS MF7460, Cubify CubeX, Okidata — appear in the top 10 for only one year reflecting one-off, low-volume, high-value purchases rather than a consistent pricing/sales pattern.
- Cisco TelePresence System commands the highest AOV at $22,638 — a direct result of being sold as a single unit each time
- Canon imageCLASS follows at $12,319, with Cubify CubeX 3D Printer close behind at $7,999
- Eureka Disposable Bags recorded the lowest AOV at just $1.62.

</td>

<td width="33.3%" valign="top">

### Consistent Products
- Among top-selling products, Fellowes PB500 tops the revenue chart at $27,453, followed by HON 5400 Series Task Chairs ($21,870), while Logitech P710e Mobile Speakerphone trails the **top 10** at $10,196
- Hewlett Packard LaserJet, Fellowes PB500 Electric Punch, Logitech P710e Mobile Speakerphone, Global Troy, GBC DocuBind, and Plantronics CS510 all show sharp year-over-year swings. Despite the volatility, their growth potential warrants continued monitoring to determine whether these are driven by inconsistent demand or one-off purchasing spikes.
- Most of these **top 10 consistent products** showed high volatility, with only HON 5400 Series Task Chairs and SAFCO Arco Folding Chair proving relatively less volatile but the most stable one is HON 5400 shows a healthier growth trajectory (+10%, -12%, +56%), while SAFCO Arco never fully bounces back after a steep -52.9% drop in 2016 making it less relaible .
- DMI Eclipse demonstrates both declining growth and unstable performance, suggesting weakening market relevance.


</td>


</tr>
</table>

<img width="1076" height="360" alt="Screenshot 2026-09-23 011032" src="https://github.com/user-attachments/assets/d4d974b9-5539-448f-882c-8d05ea347386" />

<br><br><br>
<br><br><br>

<h2 align="center">Loyalty Program Insights</h2>

<img width="1032" height="345" alt="Screenshot 2026-09-28 220909" src="https://github.com/user-attachments/assets/4078422c-1ddc-4878-b39c-91807a67c2db" />



<table>
<tr>
<td width="100%" valign="top">

- **Consistent and inconsistent** customers started at similar sales levels in 2015 and dipped sharply in early 2016. Sales fluctuated and crossed frequently through 2016–2017, with no sustained gap overall in year 2016. From 2017, inconsistent customer sales grew faster, widening the gap substantially in 2018.

***Note**:For Non Loyal Customers, new customers from **2018** was **excluded** from the total **500** Non-Loyal Customers cause there was no further years to track the behavior of these customers, thus the value is derived (500-11=489 customers)*

- **Customer Trends Over the Years**
1. **2015–2016:** Customer Base fell from 589 to 567 with 141 new customers, 426 retained and 163 churned.
2. **2016–2017:** Customers increased to 635 with 52 new customers, 444 retained, 123 churned and 139 reactivated (active in 2015, inactive in 2016).
3. **2017–2018:** Customer count grew to 690 with 11 new customers, 552 retained, 83 churned and the remaining 127 were reactivated customers (active in 2015/2016, inactive in 2017).
4. **Pattern**: Churn steadily dropped (163 → 123 → 83), while retention climbed (426 → 444 → 552) — stability improved through lower churn and higher retention, but growth now relies on reactivating lapsed customers, as new customer acquisition fell from 141 to 11 (141 → 52 → 11).
</tr>
</table>

<br><br><br>

<h2 align="center">Regional Performance</h2>

<img width="981" height="446" alt="Screenshot 2026-09-29 235608" src="https://github.com/user-attachments/assets/f278ae97-51ed-49a6-bb15-18c087c31bf1" />

<table>
<tr>
<td width="100%" valign="top">

### Regional Overview 

| Rank | Region  | Revenue 2015 → 2018 | Revenue Growth | Order Growth |
|------|---------|---------------------|----------------|--------------|
| 1    | West    | $145,907 → $248,130 | +70%           | +72.1% (308 → 530) |
| 2    | East    | $127,652 → $210,129 | +64.6%         | +81.2% (255 → 462) |
| 3    | Central | $102,920 → $141,627 | +37.6%         | +79.4% (223 → 400) |
| 4    | South   | $103,374 → $122,164 | +18.2%         | +67.1% (161 → 269) |


- **West:** Top performer. Revenue dipped slightly in 2016, then grew sharply in 2017 ($182,471) and 2018. Orders rose every year.
- **East:** Steady, consistent growth with the highest order growth of all regions.
- **Central:** Moderate growth. Revenue peaked in 2017 and dipped slightly in 2018, showing slowing momentum.
- **South:** Weakest performer. Revenue fell to $70,076 in 2016 and recovered only partially by 2017 ($93,535), with a stronger rebound in 2018. Order volume is improving, but the region still lags behind the others.

### Top States By Region


**West**
- **California:** Largest contributor in the region. Dipped 4.3% in 2016, then grew in 2017 and 2018.
- **Washington:** Declined 33.1% in 2016 and 0.8% in 2017, then surged 230.8% in 2018.

**East**
- **Pennsylvania:** Best growing state, with positive growth every year.
- **New York:** Volatile but strong. Grew 20.3% in 2016, fell 8.5% in 2017, then rebounded 32.4% in 2018.
- **Ohio:** Grew in 2016 and 2017 but dropped 11.4% in 2018, signaling emerging weakness.

**Central**
- **Illinois:** Stable performer with positive growth every year.
- **Michigan:** Explosive growth in 2016 and 2017, but fell 5.3% in 2018, making it unstable.
- **Texas:** Highest revenue in the region. Fell sharply by 32.2% in 2016, then grew in 2017 and 2018, though recovery has been slow.

**South** (weakest region)
- **North Carolina:** Steady growth. Dipped 0.7% in 2016, then grew 74.9% in 2017 and 53.8% in 2018.
- **Florida:** Fell 58.4% in 2016 and 5% in 2017, then rebounded 95.5% in 2018.
- **Virginia:** Highly volatile (-59.1%, +153.2%, -71.5%), making it a high-risk state.


</tr>
</table>

<img width="1132" height="555" alt="Screenshot 2026-09-30 133826" src="https://github.com/user-attachments/assets/ed0a18c0-c14c-4b4a-ac92-b6572a1f198a" />

## Recommendations

**Based on the insights, here are some recommendations**
<table>
<tr>
<td width="100%" valign="top">

### Sales

#### Sales (Quarterly and Monthly)

Q1: Treat March as the anchor month, keep February targets realistic, and confirm whether January's 2018 surge is repeatable.

Q2: Reverse April's decline early with retention campaigns and no stock-outs, and don't chase May's 2017 peak.

Q3: Plan inventory and capacity ahead of September, and check whether August's 2018 surge was sustainable before raising its budget.

Q4: Concentrate promotions and stock in October and November, investigate the drop in 2018, and hold pricing in December, since volume still above 2015, 2016.

#### Average Order Value

- Protect premium pricing in Q1, and use bundles and cross-selling in Q2 and Q3 to lift basket size without relying on discounts.

- Run A/B tests in Q4 to find what drove the 2017 AOV peak, make it repeatable and identify the drops in 2016 and 2018 whether caused by low valued customer or weaker product mix.

#### Order Count and AOV Together

- 2016 and 2018 were volume-driven years (more orders, lower AOV), which suggests heavy discounting or smaller baskets. Use minimum order thresholds, upselling, and premium bundles to turn order volume into higher revenue per order.

- 2017 was a recovery year where both AOV and order count increased, except in Q3, where AOV dropped, likely due to high-volume sales of lower-priced. Can use premium bundle pricing and cross-selling to increase AOV


### Products
**Top Products**
- HON 5400 Series Task Chairs: Best candidate for investment, generating ~$21K in revenue with 14.9% CAGR and the lowest CV (0.22), indicating stable sales and predictable growth.

- HP LaserJet 3310: Strong growth potential, with ~$18K revenue and 72.6% CAGR. However, its high CV (0.85) warrants cautious investment.

- Fellowes PB500 & GBC DocuBind TL300: Both generate high revenue and sell consistently across all four years, but CVs above 0.90 indicate high volatility. Hold and investigate before making further investment decisions.

- Canon imageCLASS 2200 Copier: Highest revenue generator (~$61K), but sales data covers only 2017–2018. Monitor future performance before committing further investment.

- Cisco TelePresence EX90: Generated ~$22.6K from a single order in 2015, with no subsequent sales. Treat as a one-time transaction rather than evidence of recurring demand; avoid inventory allocation based on historical revenue alone.

Deprioritize low-revenue products such as Avery 479, Computer Printout Index Tabs, and Acco Economy Flexible Poly Round Ring Binder, as their combined sales contributed only 0.0016% of total revenue over the four-year period and applying the same approach to other products with negligible revenue contributions.

