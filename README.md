### DSA-CAPSTONE-PROJECTS
## Amazon Product Review and Analysis
### About This Project
 Excel Pivot Dashboard analyzing product sales,reviews,discounts and pricing with KPI cards.

It gives insights on product ratings,discounts,pricing patterns and customer reviews amingst different products.

### DATA SOURCE 
Dta was provided by DSA (The Incubator Hub)
 
# Data cleaning  Actions
Before analysis,several data cleaning steps were applied to make the dataset analysis ready.

# Steps
.shortening proper to reduce long product name for a clean chart
=TRIM(LEFT(B2,FIND(" ",B2,FIND(" ",B2,FIND(" ",B2)+1)))

.Proper Case formatting 
=proper (C2)

.Removing Extra Spaces for clean fields
=TRIM(C2)

. Columb hiding 


DELIMITING: Splitting category names  

. Conversion of currency text ti numbers 

. Created Price Range Buckets

. Discount Calculation 

### DATA SOURCES

THE TOOLS USED 
- MICROSOFT EXCEL (DOWNLOAD HERE)
  1. FOR DATA CLEANING AND ANALYSIS
  2. FOR DATA ANALYSIS




### Analysis Tasks
These business questions were answered using PivotTables, charts, helper columns, and calculated fields:

1.What is the average discount percentage by product category?

2.How many products are listed under each category?

3.What is the total number of reviews per category?

4.Which products have the highest average ratings?

5.What is the average actual price vs. the discounted price by category?

6.Which products have the highest number of reviews?

7. How many products have a discount of 50% or more?
  
8. What is the distribution of product ratings (e.g., 3.0, 4.0, etc.)?

 9. What is the total potential revenue (Actual Price × Rating Count) by category?
  
10. How many unique products fall into each price range bucket?
 
11. How does rating relate to the level of discount?
  
12. How many products have fewer than 1,000 reviews?
   
13.  Which categories have products with the highest discounts?

14.Identify the top 5 products in terms of rating and number of reviews combined.

### KPI Summary (from Excel Dashboard)
Metric	Value	Insight

Total Products	1350	Unique products analyzed

Number of Product name and Products ID	1350	Suggests product name and product id duplication; cleaned during processing

Total Potential Revenue	₹ 14B+	Based on price × review count

Average Rating Overall	4.09	Indicates high customer satisfaction

Total Reviews	2,380,431	High engagement from users

Average Discount	47%	Aggressive discounting across most products

Products with ≥50% Discount	602	Nearly half of all products are heavily discounted

### Key Insights from the Dashboard


High Discount Prevalence: Nearly half of all products (over 600) have discounts of 50% or more, suggesting aggressive price-cutting as a competitive strategy.

Customer Engagement: The dataset shows over 2.3 million reviews across all products, with an average rating above 4.0, indicating strong user activity and overall product satisfaction.


Top Performing Products: Products that rank highest in both rating and number of reviews tend to be in electronics and smartphone categories.


Category Revenue Trends: Categories like Mobiles and Laptops generate significantly more potential revenue based on actual price × review count.

Price Distribution: Most products fall in the ₹200–₹500 and >₹500 ranges, indicating a focus on mid-to-premium pricing segments.

