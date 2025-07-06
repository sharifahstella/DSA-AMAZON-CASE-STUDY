# Case Study 1: Amazon Product Review Analysis
## 1. Title Description
This an analysis of product and customer review data to generate insights that can
guide product improvement, marketing strategies, and customer engagement.

## 2. Dataset Description
The dataset contains information scraped from Amazon product pages, including:
- Product details: name, category, price, discount, and ratings
- Customer engagement: user reviews, titles, and content
- Each row represents a unique product, with aggregated reviewer data
stored as comma-separated values

Total Records: 1,465 rows
TotalFields: 16 columns

## 3.Data Cleaning
This document describes the process used to clean and enrich a product dataset for improved clarity and search optimization. The main objectives were:
- To ensure data consistency and completeness
- To extract and standardize product categorization
- To generate a concise short_title feature for category Column

Identified Issues
During initial exploration, the following issues were identified:
- The category column contained hierarchical categories separated by pipe symbols (|).
- Some records had missing or inconsistent category values.

Short Title Creation
Objective
The goal was to generate a concise and SEO-friendly title that:
- Clearly identifies the product
- Highlights the most specific category
- Is limited to a manageable character length for display.

## 4.Pivot Tables Report
1. Average discount percentage by product category

The CableConnectionProctectors category with the highest discount percentage indicating that may be highly competitive and Discounts are likely used to stimulate sales or clear inventory.Therefore the categories with the lowest discount percentage could have perceived high demand or value and Sellers may maintain margins with fewer promotions.
The variation in discount levels across categories points to category-specific pricing strategies.
Below is bargraph summarising the representation.

![image](https://github.com/user-attachments/assets/78c89da0-ea30-422d-be53-82b1b2411c78)

2. Products are listed under each category

The USBCables category has the largest number of products, representing the widest assortment.
SecureDigitalCards have fewer products, indicating potential opportunities for assortment expansion if supported by demand.
A balanced mix of categories suggests diversified offerings catering to various customer interests.

3. Total number of reviews per category

Electronics and Home & Kitchen have the highest total number of reviews, indicating that Strong customer interest and engagement and Potentially higher sales volumes or more frequent purchases.Categories have lower total reviews, suggesting Either smaller assortments or less customer interaction.High review counts can also signal greater social proof (i.e., more reviews boost buyer confidence). therefore below is a column bar graph

![image](https://github.com/user-attachments/assets/b6197c62-071b-405b-89ba-1f529b8e1019)
 
4. Products with the highest average ratings

USBCables and Mice product categories feature prominently among the highest-rated items, suggesting these categories combine strong perceived quality with popularity.
High average ratings (4.7–5) indicate: High customer satisfaction,Strong product-market fit, and Potential for these products to be featured in promotions and best-seller lists.
Products with high ratings and large review counts (e.g., 3,200 reviews) are especially valuable, since their reputation is well-established.

5. Average Actual Price vs. Discounted Price by Category

Split-SystemAirConditioners have the highest average price before and after discounts, confirming this as a premium category.
ColouredPaper & WoodenPencils show the steepest reduction in price after discounts, reflecting aggressive discounting strategies.
The discounting varies significantly by category:
Some categories maintain higher relative prices even after discounts.Others achieve deeper discounts to attract buyers.
The difference between original and discounted price illustrates: The perceived value range customers experience.How pricing strategies differ across categories.

6. Products with the highest number of reviews

Products with the highest review counts likely Have high sales volumes,Benefit from greater visibility on the platform,Enjoy stronger social proof and buyer confidence.
USBCables categories appear prominently, confirming these as high-engagement categories.Many of these top-reviewed products also maintain strong average ratings (4.5+), suggesting both popularity and customer satisfaction.

7. Products with a discount of 50% or more

Therefore 56 products are discounted at a percentage of >=50. Allowed me to quickly assess how much of the catalog is under aggressive discounting.

8. Distribution of product ratings

The majority of products fall within the 4.0 to 5.0 rating range, indicating a generally high level of customer satisfaction.
The peak occurs at 4.5, which suggests that: Most products meet or exceed customer expectations and Negative experiences are less common.Fewer products are rated below 3.5, which is good for platform trustworthiness but may also suggest underreporting of dissatisfaction or review bias.

9. Total potential revenue (actual_price × rating_count) by category

Smartphones categories generate the highest potential revenue, driven by: Higher average prices and Larger numbers of reviews (indicating high demand).ElectricGrinders and ColouredPaper have lower potential revenue, reflecting either lower prices, fewer reviews, or both.The distribution of potential revenue suggests a concentration of engagement and purchasing power in premium categories.

10. Number of unique products per price range bucket

The 500 segment has the largest number of products, indicating this is the core pricing sweet spot for the assortment.A substantial number of products are priced 200-500, suggesting: A meaningful share of premium offerings and Potential for higher margins.The <200 bucket still represents significant variety but is the smallest segment, possibly reflecting: Lower-cost impulse items and Limited differentiation at the lowest price points. Below is a pie chart

![image](https://github.com/user-attachments/assets/4e3e9b84-abfa-4ff0-8e53-f7893cd52382)

12. Products that have fewer than 1,000 reviews

The column used from the studies the rating_count column where by found out that 326 is the count of products with fewer than 1,000 reviews.

13. Categories  that have products with the highest discounts

Split-SystemAirConditioners has the highest average discount (42%), suggesting: Highly competitive pricing and Frequent promotions to drive volume.
TraditionalLaptops and Tablets also see relatively high discounts, reflecting: A strategy to attract price-sensitive buyers and Potentially faster inventory turnover.
Smartphones, while the highest-revenue category, has the lowest average discounts, likely to: Protect margins and Maintain a premium brand perception.

14. top 5 products in terms of rating and number of reviews combined

These products combine high credibility (ratings above 4.6) with strong volume (thousands of reviews).
HDMICables dominate the top spots.
These are your flagship products, likely driving a significant share of revenue and customer trust.

# Case Study 2: Kultra Mega Stores Inventory
## Company Overview
Kultra Mega Stores (KMS), headquartered in Lagos, specializes in office supplies and furniture. Its customer base includes:
- Individual consumers
- Small businesses (retail)
- Large corporate clients (wholesale)
  
This project supports the Abuja division by analyzing historical order data (2009–2012) to provide actionable insights.


## Dataset
Source: Excel file with orders from 2009–2012
Imported Table: KMS Case Study
Key Fields:
- Order_ID
- Order_Date
- Customer_Name
- Customer_Segment
- Region
- Product_Category
- Product_Sub_Category
- Product_Name
- Quantity
- Sales
- Profit
- Shipping_Cost
- Ship_Mode
- Order_Priority
- Returned

### Case Scenario I — Analysis & SQL Queries

- Which product category had the highest sales?

```
SELECT TOP 1
    Product_Category,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Product_Category
ORDER BY 
    TotalSales DESC;

```
Technology having the highest sales 

 ![Line graph](https://github.com/sharifahstella/DSA_Kultra-Mega-Stores-Inventory/blob/main/cate.PNG) 

- Top 3 and Bottom 3 regions in terms of sales

```
SELECT TOP 3
    Region,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Region
ORDER BY 
    TotalSales DESC;

```
![Line graph](https://github.com/sharifahstella/DSA_Kultra-Mega-Stores-Inventory/blob/main/top3.PNG) 

Therefore West ,Ontario and Parie top 3 regions respectively in sales leading to the most seen regions profitably
```
SELECT TOP 3
    Region,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Region
ORDER BY 
    TotalSales ASC;

```
![Line graph](https://github.com/sharifahstella/DSA_Kultra-Mega-Stores-Inventory/blob/main/bottom3.PNG) 

 The bottom 3 regions that include Nunavit,Northwest Territories and Yukon have the least sales that need to drive attention to improve on the sales in the regions.

- Total sales of appliances in Ontario

```
SELECT
    SUM(Sales) AS TotalSalesOfAppliances
FROM 
    [dbo].[KMS Sql Case Study]
WHERE 
    Product_Sub_Category = 'Appliances'
    AND Region = 'Ontario';

```
![image](https://github.com/user-attachments/assets/bab5b458-00cd-4368-899f-85492e2a2611)


Therefore there was no total sales of appliances in Ontario which also calls for the most seen region that has to increase on the sales in the region of ontario.

- Recommendations to increase revenue from the bottom 10 customers

```
SELECT TOP 10
    Customer_Segment,
    Customer_Name,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Customer_Segment,
    Customer_Name
ORDER BY 
    TotalSales ASC;

```
![Line graph](https://github.com/sharifahstella/DSA_Kultra-Mega-Stores-Inventory/blob/main/cate2.PNG)  

Recommendations:
- 1. Personalized Engagement: Assign account managers to follow up and understand why spend is low.
- 2. Targeted Promotions: Offer exclusive discounts or loyalty rewards.
- 3. Cross-Selling: Recommend related products based on prior purchases.
- 4. Feedback Collection: Survey customers to learn about unmet needs.
- 5. Streamlined Ordering: Simplify reorder processes.
 
- Shipping method with the highest shipping cost

```
SELECT TOP 1
    Ship_Mode,
    SUM(Shipping_Cost) AS TotalShippingCost
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Ship_Mode
ORDER BY 
    TotalShippingCost DESC;

```
![image](https://github.com/user-attachments/assets/45c349c4-9493-45b8-96f9-1ef3c2c4f847)


Therefore Delivery Truck has the highest shipping cost

###Summary of Insights
- Categories and regions driving most revenue are critical for growth.
- Low-performing regions and customers offer opportunities for targeted initiatives.
- Shipping methods should be reviewed for cost efficiency.

### Case Scenario II — Analysis & SQL Queries

- most valuable customers, and what products or services do they typically purchase

```
SELECT TOP 5
    Customer_Segment,
    Customer_Name,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
GROUP BY 
    Customer_Segment, Customer_Name
ORDER BY 
    TotalSales DESC;


SELECT 
    Customer_Segment,
    Customer_Name,
    Product_Category,
    SUM(Sales) AS CategorySales
FROM 
    [dbo].[KMS Sql Case Study]
WHERE 
    Customer_Segment IN (
        SELECT TOP 5 Customer_Segment
        FROM [dbo].[KMS Sql Case Study]
        GROUP BY Customer_Segment
        ORDER BY SUM(Sales) DESC
        
    )
GROUP BY 
    Customer_Segment, Customer_Name, Product_Category
ORDER BY 
    Customer_Segment, CategorySales DESC;

```

![image](https://github.com/user-attachments/assets/965f0c41-e690-458b-8257-8115a927e7ef)

![image](https://github.com/user-attachments/assets/74432272-b004-422c-8be8-7ca9dd81b092)

- small business customer with the highest sales

```
SELECT TOP 1 
    Customer_Segment,
    Customer_Name,
    SUM(Sales) AS TotalSales
FROM 
    [dbo].[KMS Sql Case Study]
WHERE 
    Customer_Segment = 'Small Business'
GROUP BY 
    Customer_Segment, Customer_Name
ORDER BY 
    TotalSales DESC;

```
![image](https://github.com/user-attachments/assets/76412398-e9ab-4056-8d45-a769827f3068)

The small bussiness customer is Dennis Kane to secure repeat business.

- Corporate Customer That placed the most number of orders in 2009 – 2012

```
SELECT TOP 1
    Customer_Segment,
    Customer_Name,
    SUM(Order_ID) AS OrderCount
FROM 
    [dbo].[KMS Sql Case Study]
WHERE 
    Customer_Segment = 'Corporate'
    AND Order_Date BETWEEN '2009-01-01' AND '2012-12-31'
GROUP BY 
    Customer_Segment, Customer_Name
ORDER BY 
    OrderCount DESC;

```
![image](https://github.com/user-attachments/assets/ac9a7e1d-5f36-4b57-8610-52658d6e085a)


Bill Eplette was the corprate customer that placed a number of orders therefore may be a priority for volume-based incentives or preferred service agreements.

- consumer customer that was the most profitable one

```
SELECT TOP 1 
    Customer_Segment,
    Customer_Name,
    SUM(Profit) AS TotalProfit
FROM 
    [dbo].[KMS Sql Case Study]
WHERE 
    Customer_Segment = 'Consumer'
GROUP BY 
    Customer_Segment, Customer_Name
ORDER BY 
    TotalProfit DESC;

```
![image](https://github.com/user-attachments/assets/fbaa1608-7beb-4bc4-afcf-2001909baeef)


Emily Phan was the most profitable customer that insight support strategies to grow profits in the Consumer segment.

- Which customer returned items, and what segment do they belong to?

```
SELECT DISTINCT
    o.[Customer_Name],
    o.[Customer_Segment]
FROM
      [dbo].[KMS Sql Case Study] o
INNER JOIN
    Order_Status s ON o.[Order_ID] = s.[Order_ID]
WHERE
    s.[Status] = 'Returned'
ORDER BY
    o.[Customer_Segment], o.[Customer_Name];

```
![image](https://github.com/user-attachments/assets/bf0176ef-abe9-443a-959f-78a87667b6a8)

- Did the company appropriately spend shipping costs based on Order Priority?

I analyzed shipping behavior by priority and shipping mode.

```
SELECT
    o.[Order_Priority],
    o.[Ship_Mode],
    SUM(o.[Order_ID]) AS OrderCount,
    SUM(o.[Shipping_Cost]) AS TotalShippingCost
FROM
    [dbo].[KMS Sql Case Study] o
GROUP BY
    o.[Order_Priority], o.[Ship_Mode]
ORDER BY
    o.[Order_Priority], o.[Ship_Mode];
```

![image](https://github.com/user-attachments/assets/51a2302d-fd6d-4aa6-9e02-4f316fe4f7ee)


### Summary of Recommendations
If you observe that Low or Medium priority orders often use Express Air, this indicates unnecessary shipping cost.
KMS should implement a shipping policy:
- Use Express Air only for Critical/High priority orders
- Use Delivery Truck for Medium/Low orders to reduce costs
- Regularly review shipping behavior to align with order urgency


