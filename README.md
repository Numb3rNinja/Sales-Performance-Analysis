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
   - Confirm **Order Date** and **Ship Date** are Date type, **Sales** is Decimal Number or Currency, and **Row ID**, **Order ID**, **Customer ID**, **Product ID**, **Postal Code** are Text in **Data View** or **Modeling** > **Properties**. Correct any mismatches.  
2. **Missing Values**:  
   - Check **Sales**, **Order Date**, **Region**, **Category**, and **Segment** for nulls or blanks in **Data View** or **Power Query**. Replace blanks with “Unknown” for non-critical fields (e.g., Segment) using **Transform Data** > **Replace Values**. Flag critical missing data (e.g., Sales) for correction.  
3. **Duplicate Rows**:  
   - Use **Row ID** or **Order ID** in **Power Query** to identify duplicates (**Group By** or **Remove Duplicates**). Remove duplicates if they inflate sales totals.  
4. **Outlier Detection**:  
   - Sort **Sales** in **Data View** to check for anomalies (e.g., negative or excessively high values). Investigate and correct errors (e.g., refunds, data entry issues) in **Power Query**.  
5. **Date Consistency**:  
   - Verify **Order Date** range in **Data View** (min/max dates). Flag and correct outliers (e.g., future dates like 2050) in **Power Query**.  
6. **Geographic Consistency**:  
   - Ensure **Region**, **State**, and **City** have consistent naming (e.g., no “West” vs. “Wst”) in **Power Query**. Set **Data Category** to **Place** for map visuals in **Modeling**.  

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
Sales in 2017—and especially in 2018—were substantially higher than in 2015 and 2016. Many months in 2018 saw sales that doubled or even tripled their 2015 counterparts. November 2018 marked the peak in monthly sales at \$117,938, while February 2015 recorded the lowest monthly sales at \$4,520. Despite being a strong year overall, February 2018 stands out as a notable low point.
All three product categories contributed significantly to overall sales, with Technology maintaining a slight lead. Consumer sales were the primary driver, accounting for approximately half of all revenue by segment. Revenue was heavily concentrated in the Technology (Phones) and Furniture (Chairs, Tables) sub-categories, while sub-categories within Office Supplies made up the lowest performers.
Although California led in total sales volume, New York and Washington generated significantly higher revenue per transaction.

![Image](https://github.com/user-attachments/assets/4de12f97-f9be-4306-97a6-b7faee9d3626)
