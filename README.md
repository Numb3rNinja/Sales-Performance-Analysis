# Sales Performance Analysis

## Project Background
In today’s fast-paced retail and business environment, organizations manage vast volumes of transactional data across diverse product categories, geographic regions, and customer segments. Understanding sales performance is critical for driving revenue growth, optimizing resource allocation, and enhancing strategic decision-making. The ability to transform raw sales data into actionable insights enables businesses to identify high-performing products, target underperforming regions, and tailor strategies to specific customer segments, ultimately strengthening their competitive edge.
This project was undertaken to address the challenge of converting transactional sales data into a concise, actionable business intelligence tool. By leveraging Power BI, the project aims to create an interactive sales performance dashboard that provides clear, data-driven insights to support operational efficiency, strategic planning, and stakeholder communication. The dashboard, limited to six visuals, focuses on delivering high-impact insights to maximize business outcomes.

**Key Insights and Recommendations Focused On:**
1. **Sales Trends Over Time**:  
   - **Purpose**: Analysing sales patterns over months or quarters (using Order Date and Sales) to identify seasonal trends, peak periods, and potential demand shifts.  
   - **Business Value**: Informs inventory planning, promotional scheduling, and staffing adjustments to capitalize on high-demand periods and mitigate low-performance seasons.  

2. **Regional Sales Performance**:  
   - **Purpose**: Evaluating sales distribution across regions (Region, State, City) to identify top-performing areas and regions requiring intervention.  
   - **Business Value**: Guides localized marketing strategies, resource allocation (e.g., sales teams), and expansion decisions to optimize regional performance.  

3. **Product and Category Performance**:  
   - **Purpose**: Identifying top-selling products (Product Name) and high-performing categories (Category, Sub-Category) to understand revenue drivers.  
   - **Business Value**: Supports inventory optimization, merchandising strategies, and targeted promotions to boost sales of high-margin products and address underperforming ones.  

4. **Customer Segment Analysis**:  
   - **Purpose**: Assessing sales by customer segment (e.g., Consumer, Corporate, Home Office) to uncover purchasing behaviors and preferences.  
   - **Business Value**: Enables tailored marketing campaigns, loyalty programs, and account management strategies to enhance customer retention and increase sales within key segments.  

**Data Structure & Initial Checks**
The dataset for this project consists of a single table with 10,000 rows, capturing detailed sales transactions. The table includes the following columns:  
- **Row ID**: Unique record identifier (Text).   
- **Order ID**: Unique order identifier (Text).   
- **Order Date**: Date of order placement (Date).  
- **Ship Date**: Date of shipment (Date).   
- **Ship Mode**: Shipping method (Text).   
- **Customer ID**: Unique customer identifier (Text).   
- **Customer Name**: Customer name (Text). 
- **Segment**: Customer segment (e.g., Consumer, Corporate, Home Office) (Text). 
- **Country, City, State, Postal Code**: Geographic fields (Text).  
- **Region**: Geographic region (Text). 
- **Product ID**: Unique product identifier (Text).   
- **Category, Sub-Category**: Product classification (Text).   
- **Product Name**: Specific product (Text).   
- **Sales**: Revenue generated (Decimal Number/Currency). 


**Key Early Checks**:  
1. **Data Type Validation**:  
   - Confirming **Order Date** and **Ship Date** are Date type, **Sales** is Decimal Number or Currency, and **Row ID**, **Order ID**, **Customer ID**, **Product ID**, **Postal Code** are Text in **Data View** or **Modeling** > **Properties**. Correcting any mismatches.  
2. **Missing Values**:  
   - Checking **Sales**, **Order Date**, **Region**, **Category**, and **Segment** for nulls or blanks in **Data View** or **Power Query**. Replacing blanks with “Unknown” for non-critical fields (e.g., Segment) using **Transform Data** > **Replace Values**. Flaging critical missing data (e.g., Sales) for correction.  
3. **Duplicate Rows**:  
   - Using **Row ID** or **Order ID** in **Power Query** to identify duplicates (**Group By** or **Remove Duplicates**). Removing duplicates if they inflate sales totals.  
4. **Outlier Detection**:  
   - Sorting **Sales** in **Data View** to check for anomalies (e.g., negative or excessively high values). Investigating and correcting errors (e.g., refunds, data entry issues) in **Power Query**.  
5. **Date Consistency**:  
   - Verifying **Order Date** range in **Data View** (min/max dates). Flag and correct outliers (e.g., future dates like 2050) in **Power Query**.  
6. **Geographic Consistency**:  
   - Ensuring **Region**, **State**, and **City** have consistent naming (e.g., no “West” vs. “Wst”) in **Power Query**.
     
**Stakeholders**  
- **Sales Managers/Executives**: Monitor performance and set targets.  
- **Business Analysts**: Inform forecasting and planning.  
- **Marketing/Product Teams**: Develop targeted campaigns and product strategies.  
- **Investors/Leadership**: Review performance for strategic decisions.  

**Scope**    
- **Tool**: Power BI Desktop, with optional publishing to Power BI Service.  
- **Exclusions**: Metrics beyond sales (e.g., profit).  

**Deliverables**  
- Power BI (.pbix) file with the dashboard.  
- Documentation of creation steps.  


# Executive Summary
## Overview of Findings
Sales in 2017—and especially in 2018—were substantially higher than in 2015 and 2016. Many months in 2018 saw sales that doubled or even tripled their 2015 counterparts. November 2018 marked the peak in monthly sales at $117,938, while February 2015 recorded the lowest monthly sales at $4,520. Despite being a strong year overall, February 2018 stands out as a notable low point.
All three product categories contributed significantly to overall sales, with Technology maintaining a slight lead. Consumer sales were the primary driver, accounting for approximately half of all revenue by segment. Revenue was heavily concentrated in the Technology (Phones) and Furniture (Chairs, Tables) sub-categories, while sub-categories within Office Supplies made up the lowest performers.
Although California led in total sales volume, New York and Washington generated significantly higher revenue per transaction.

![Image](https://github.com/user-attachments/assets/4de12f97-f9be-4306-97a6-b7faee9d3626)   


## Insights Deep-Dive
**Sales by Category**  

Over the comprehensive 3.5-year period spanning 2015 to 2018, the sales performance across the three primary product categories demonstrated remarkable stability in their competitive positioning. **Technology** emerged as the undisputed leader, generating **$827,456 in cumulative revenue** and accounting for **36.6% of the organization's total sales** of $2,261,000. This category maintained a significant and consistent advantage over its counterparts. **Furniture** secured a steady second place with **$728,659 in sales (32.2% of the total)**, while **Office Supplies** trailed slightly behind at **$705,422 (31.2% of total sales)**.  

The performance gaps between categories proved to be persistent throughout the period. Technology's revenue lead over Furniture amounted to **$98,797, representing a substantial 13.4% advantage**. Its lead over the Office Supplies category was even more pronounced at **$122,034, equating to a 17.3% difference**. Meanwhile, Furniture maintained a relatively narrow margin over Office Supplies, outperforming it by **$23,237 or 3.4%**, highlighting a closer competition between these two segments.  

These patterns carry important strategic implications. **Technology's sustained dominance** is particularly noteworthy, as it maintained its revenue leadership despite potential annual market fluctuations, such as the noted downturn in 2018. This resilience strongly suggests deeply entrenched product demand, possibly driven by technological refresh cycles, essential business infrastructure needs, or robust B2B/client relationships that provide a stable revenue base. **Furniture's consistent second-place performance** indicates reliable demand, likely fueled by big-ticket items such as desks and chairs which command higher unit prices, contributing to its steady revenue stream even without the top position. Conversely, the **Office Supplies category's position as the lowest revenue generator** presents a strategic concern. Its underperformance is notable given the presumably high purchase frequency of its items, potentially pointing to challenges such as lower average order values (AOV), intense market competition, commoditization pressures, or thinner margins that limit its overall revenue contribution despite volume. This consistent hierarchy and the underlying drivers revealed by the multi-year data provide critical insights for resource allocation, product development focus, and category management strategies moving forward.
![Image](https://github.com/user-attachments/assets/cd4b43ab-2e99-47be-a7a3-9b639a9c055e)  

**Sales by Segment** 

The sales distribution across customer segments reveals a highly concentrated revenue landscape dominated by the **Consumer segment**, which contributed **50.76% of total sales** over the 3.5-year period. This overwhelming share—equivalent to 2.7 times the Home Office segment and 1.7 times Corporate sales—highlights the critical role of B2C demand in driving revenue. The strength here likely stems from high-volume purchases of popular sub-categories like Phones ($327K) and Chairs ($323K), amplified by e-commerce efficiency and recurring individual purchases. By contrast, the **Corporate segment captured 30.44% of revenue**, reflecting moderate but underutilized potential given its alignment with premium, bulk-friendly categories like Furniture and Technology (which jointly generated 63% of category sales). This gap suggests untapped opportunities in enterprise contracts or institutional buyers. Most notably, the **Home Office segment significantly underperformed at just 18.79%**—a concerning figure given rising remote-work trends during this period. This disconnect implies ineffective targeting (e.g., marketing corporate-grade products to cost-sensitive individuals) or missed bundling opportunities for remote workers.  

Strategically, Consumer dominance warrants reinforced loyalty programs and e-commerce optimization to sustain volume-driven growth. However, over-reliance on this segment exposes vulnerability to economic downturns impacting discretionary spending. Meanwhile, Corporate’s unrealized potential demands urgent initiatives like curated "Office Setup Suites" (e.g., Chairs + Tables + Storage) with volume discounts to convert bulk buyers. For Home Office, repositioning is essential: bundling high-demand items (e.g., Binders + Phones + Chairs) into affordable "Remote Work Kits" could bridge the gap between Consumer convenience and Corporate quality. Crucially, margin analysis is needed—Corporate’s higher average order values (e.g., like Wyoming’s $1,603 AOV) likely yield better profitability than Consumer’s high-volume/low-margin sales, urging a rebalance toward B2B expansion. Without intervention, geographic and segment hyper-focus on coastal Consumers risks long-term resilience, making Corporate and Home Office diversification a revenue-stabilizing imperative.
![Image](https://github.com/user-attachments/assets/42a1340f-1ff5-4b28-b31b-8d1f0fbeefd1)
