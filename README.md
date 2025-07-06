# DSA-AMAZON CASE STUDY

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

## 3.Data Cleaaning
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
- 1. Average discount percentage by product category

The product category with the highest discount percentage.Below is bargraph summarising the representation with CableConnectionProctectors.

![image](https://github.com/user-attachments/assets/78c89da0-ea30-422d-be53-82b1b2411c78)

- 3. Products are listed under each category
  

- 4. Total number of reviews per category

![image](https://github.com/user-attachments/assets/b6197c62-071b-405b-89ba-1f529b8e1019)
 
5. Products with the highest average ratings
6. Average Actual Price vs. Discounted Price by Category
7. Products with the highest number of reviews

8. Products with a discount of 50% or more

Therefore 56 products are discounted at a percentage of >=50. Allowed me to quickly assess how much of the catalog is under aggressive discounting.

9. Distribution of product ratings
10. Total potential revenue (actual_price × rating_count) by category
11. Number of unique products per price range bucket

![image](https://github.com/user-attachments/assets/4e3e9b84-abfa-4ff0-8e53-f7893cd52382)

12. How many products have fewer than 1,000 reviews?

The column used from the studyis the rating_count column where by found out that 326 is the count of products with fewer than 1,000 reviews.
