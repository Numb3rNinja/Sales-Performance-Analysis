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
- Power BI [sales performance analysis.pbix](https://github.com/Numb3rNinja/Sales-Performance-Analysis-Dashboard.git) file with the dashboard.  
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

![Image](https://github.com/user-attachments/assets/42a1340f-1ff5-4b28-b31b-8d1f0fbeefd1)  


**Sales Trend**
  
Sales trend reveals a compelling narrative of robust growth punctuated by distinct seasonal rhythms and notable anomalies over the 4-year period. A clear upward trajectory emerges despite temporary setbacks, with total annual sales climbing from **$479,856 in 2015** to **$722,052 in 2018**. This progression was interrupted only in **2016**, which experienced a 4.26% year-over-year (YoY) decline to **$459,436**, likely indicating market challenges or operational headwinds. The subsequent recovery proved exceptionally strong, however, with sales surging **30.64% in 2017 ($600,191)** and accelerating further with **20.31% growth in 2018 ($722,052)**. This rebound, particularly during 2017–2018, signals successful strategic adjustments and expanding market traction.

Seasonality dominates the sales pattern, with **Q4 (September–December)** consistently emerging as the peak performance window. High-impact months include **September 2015 ($81,624)**, **December 2017 ($95,739)**, and the dataset’s pinnacle, **November 2018 ($117,938)**. November alone peaked in three of the four years (2015, 2017, 2018), underscoring its role as a critical year-end revenue driver. Conversely, **February** annually recorded the weakest results, hitting an extreme low of **$4,520 in 2015** – a potential outlier possibly influenced by external disruptions or data anomalies. Q1 (January–March) consistently demonstrated high volatility, exemplified by erratic YoY swings like **January 2018 ($43,476)** versus **January 2015 ($14,206)**.

Anomalies further define the trend’s character. The **2016 underperformance** was particularly pronounced in traditionally strong months, with **March 2016 ($32,339)** plummeting **41.4% below March 2015 ($55,206)**. Conversely, **2018 delivered exceptional surges**, including **August 2018 ($62,838)** – an unprecedented summer performance representing a **105.7% YoY jump** – and the record-breaking **November 2018 ($117,938)**, which soared **49.2% above its 2017 counterpart**. Critically, the **second half (H2: July–December)** consistently outperformed the first half (H1: January–June), averaging **$53,940/month versus $30,240/month** and contributing **64% of annual volume**. This H2 dominance intensified over time, with peak values escalating annually (e.g., **December 2017’s $95,739** to **November 2018’s $117,938**). Encouragingly, while seasonal troughs persisted, their severity lessened post-2015, as seen in February’s improvement from **$4,520 (2015)** to **$19,921 (2018)**, suggesting improved demand planning or market stabilization. These dynamics highlight both the cyclical nature of demand and the organization’s growing capacity to capitalize on high-potential periods while mitigating traditional slowdowns.
![Image](https://github.com/user-attachments/assets/9d6fc795-5653-4f7e-b27c-658eb520275f)  


**Sales by Sub-Category**

The sales distribution across sub-categories reveals an extreme and strategically significant disparity in revenue contribution. A dominant cluster of **five high-performing sub-categories** drives the overwhelming majority of revenue: **Phones (Technology)** lead with **$327,782**, closely followed by **Chairs (Furniture)** at **$322,823**. They are supported by **Storage (Technology)** at **$219,343**, **Tables (Furniture)** at **$202,811**, and **Binders (Office Supplies)** at **$200,029**. In stark contrast, the **bottom five sub-categories** contribute minimally to overall revenue, all belonging to Office Supplies: **Fasteners ($3,002)**, **Labels ($12,348)**, **Envelopes ($16,128)**, **Art ($26,705)**, and **Supplies ($46,420)**.  

This performance gap translates into profound revenue concentration. The **top five sub-categories collectively generated $1,272,788**, dwarfing the **bottom five’s meager ~ $104,603**. The dominance of the leaders is further underscored by the fact that **Phones and Chairs alone ($650,605 combined) outsell the entire bottom five by a factor of 6.2x**. The disparity reaches its peak when comparing the top performer to the weakest: **Phones generates a staggering 109 times more revenue than Fasteners**. Even within the extremes, **Binders outperforms the highest-ranked bottom-five sub-category (Supplies) by 4.3x**.  

Category alignment further illuminates underlying trends. **Technology** demonstrates consistent strength, with **Phones (#1 overall)** and **Storage (#3 overall)** both residing in the top tier. **Furniture** similarly relies on its core products, **Chairs (#2)** and **Tables (#4)**, as primary revenue pillars. **Office Supplies**, however, presents a glaring imbalance: while **Binders (#5 overall)** stands as its lone high performer, the category is disproportionately represented in the bottom tier, claiming all five of the lowest-ranking sub-categories.  
  
This extreme concentration necessitates a focused strategy. **Phones and Chairs**, virtually tied for the top position, represent critical strategic assets. Their success likely stems from high demand drivers like remote work trends (Phones) and ergonomic needs (Chairs), combined with premium pricing potential. **Storage and Tables** further indicate robust demand in infrastructure and workspace solutions, likely tied to B2B or corporate expansion. Conversely, **Office Supplies faces a systemic challenge**. Beyond the standout success of Binders, the category is mired in underperformance. Sub-categories like Fasteners, Labels, and Envelopes suggest severe commoditization, low customer priority, or operational inefficiencies – characteristics of low-value, bulk-purchased items that generate negligible margin or strategic advantage. The fundamental inconsistency is clear: while Technology and Furniture exhibit balanced strength across key sub-categories, Office Supplies (with the sole exception of Binders) lags significantly, demanding a strategic reassessment of its product portfolio, pricing, and market positioning to avoid becoming a drag on overall growth.

![Image](https://github.com/user-attachments/assets/1a3704fc-172c-494e-b821-45aea350d7be)  


**Sales by States**

The geographic distribution of sales reveals extreme concentration and critical strategic patterns across the U.S. market. **Five states dominate revenue generation**, collectively driving approximately **90% of total sales**, with **California** standing as the undisputed anchor market at **$446,306** – representing **36.5% of the top five’s contribution alone**. **New York** follows as a high-value powerhouse at **$306,361**, leveraging premium average order values (**$279 per order**). **Texas** ranks third with **$168,573** in sales, though its significantly lower average order value (**$173**) suggests volume-driven, price-sensitive transactions. **Washington** ($135,207) mirrors New York’s premium positioning with a **$268 average order value**, while **Pennsylvania** ($116,277) rounds out the core revenue drivers. In stark contrast, the **bottom five states** – including **Wyoming ($1,603)**, **South Dakota ($1,316)**, **Maine ($1,271)**, **West Virginia ($1,210)**, and **North Dakota ($920)** – contribute a negligible **<0.3% of total revenue**, highlighting severe market penetration gaps outside key regions. The scale of disparity is underscored by California outselling the entire bottom five states combined by a factor of **278x**.  

**Average Order Value (AOV) patterns further segment market dynamics.** High AOV does not universally correlate with revenue scale: while **New York and Washington** successfully combine premium transaction values ($279 and $268) with high sales volume, states like **West Virginia ($302 AOV)** and **Wyoming ($1,603 AOV)** exhibit even higher per-order spending but lack critical customer volume to impact overall revenue. Conversely, **Texas ($173)** and the **Dakotas ($110–$131)** demonstrate persistently low AOV, indicating discount-driven purchasing, small-basket dominance, or operational inefficiencies in these regions. The **Wyoming anomaly** is particularly notable – its extraordinary **$1,603 AOV** (9.3x California’s $229) suggests infrequent but massive transactions, such as enterprise-level bulk purchases, though data verification is recommended to confirm this pattern.  
 
California’s dominance likely stems from population density, B2B corporate hubs (e.g., technology sectors), and mature e-commerce adoption, cementing it as the foundation of national strategy. New York and Washington exemplify the premium market model, where high-value transactions amplify revenue impact – a template for targeted expansion in similar affluent, commercialized regions. However, the **high-AOV/low-volume paradox** in states like West Virginia and Wyoming points to untapped corporate or bulk-purchasing demand that warrants focused customer acquisition efforts. Conversely, Texas and the Dakotas represent volume-oriented but margin-challenged markets, where strategies to boost basket size (e.g., bundled offerings, loyalty incentives) are essential. The extreme revenue concentration necessitates a dual approach: deepening penetration in core states while systematically diagnosing barriers in low-contribution regions – whether logistical, competitive, or sales-model related – to unlock balanced national growth.

![Image](https://github.com/user-attachments/assets/7727875f-07b0-4593-822f-a66fc5a4ca7e) 

![Image](https://github.com/user-attachments/assets/9bb6bb78-e838-487a-8ed9-29048d04d991)  


## Recommendations
- **Leverage Q4 Strength**: The consistent Q4 peaks suggest a focus on maximizing holiday season sales through targeted marketing, promotions, or inventory planning.
- **Address Q1 Weakness**: Low sales in January and February could be mitigated through off-season promotions, new product launches, or diversification to stabilize revenue.
- **Forecasting**: The predictable seasonal pattern allows for accurate sales forecasting. Businesses can use historical data to anticipate Q4 surges and plan resources accordingly.
- **Growth Strategy**: The strong year-on-year growth, especially in 2017 and 2018, suggests successful strategies that should be continued or scaled (e.g., marketing, customer acquisition, or product improvements).
Highlight Technology**: Given its lead, focus marketing efforts on Technology to maintain or grow its dominance.
- **Investigate Office Supplies**: Explore why Office Supplies lags slightly (e.g., market saturation, competition) and consider strategies like bundling with Furniture or Technology products.
- **Cross-Category Opportunities**: Since Furniture and Office Supplies are close in sales, consider cross-promotions (e.g., office setup packages) to boost both categories.
**Consumer Focus**: Maintain strong Consumer engagement through promotions, loyalty programs, or expanding high-performing sub-categories like Phones and Chairs.
- **Corporate Growth**: Target Corporate clients with tailored offerings (e.g., bulk discounts on Technology or Furniture) to increase their share, leveraging the 49.90% YoY growth from the KPI data.
- **Home Office Opportunities**: Boost Home Office sales through targeted marketing (e.g., home office bundles with Storage or Tables) or competitive pricing to capture remote workers.
- **Cross-Segment Strategies**: Explore cross-selling opportunities, such as offering Consumer-popular items (e.g., Phones) to Corporate clients or Home Office setups with Supplies to improve low-performing sub-categories.
**Top 5 Focus**: Leverage Phones and Chairs’ strong performance through targeted marketing, upselling, or product enhancements. Explore bundling Storage, Tables, and Blinders with these top performers to boost their sales.
- **Bottom 5 Strategy**: Reassess the viability of Fasteners, Labels, and Envelopes due to their low sales. Consider discontinuing or repositioning them as add-ons to high-performing sub-categories. Supplies and Art could benefit from promotions or bundling with top categories.
- **Cross-Category Opportunities**: Pair low performers (e.g., Supplies, Envelopes) with high performers (e.g., Phones, Chairs) in bundles to increase overall sales.
**Focus on High-Performing States**: Invest in marketing and operations in California, New York, and Texas to capitalize on their high sales volumes. Tailor strategies to maintain high transaction volumes in California and Texas while increasing average order values in New York and Washington.
- **Investigate Wyoming’s Outlier**: Analyze the nature of Wyoming’s sales (e.g., a single large order) to determine if it represents a niche opportunity or an anomaly.
- **Boost Sales in Low-Performing States**: Targeted marketing campaigns or promotions in states like North Dakota, West Virginia, and South Dakota could increase order volumes or average sales per order. For example, South Dakota’s low average order value suggests potential for upselling or bundling strategies.






