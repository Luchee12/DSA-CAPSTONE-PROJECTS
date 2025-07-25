
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

### BELOW ARE SCREENSHOTS OF THE ANALYSIS





[AMAZON CASE STUY.xlsx](https://github.com/user-attachments/files/21092564/AMAZON.CASE.STUY.xlsx)

### CHART REPRESENTATION [Amazon case study1  YELLOW (Recovered) 2.xlsx](https://github.com/user-attachments/files/21092575/Amazon.case.study1.YELLOW.Recovered.2.xlsx)




##### ANALYSIS OF KMS CASESTUDY
CREATE DATABASE KMS_DB

Create Table KMS_dbORDERS(
[Row_ID]INT,
[ORDER_ID]INT,
[ORDER_Date]Date,
[ORDER_Priority]varchar(50),
[ORDER_Quantity]Int,
Sales Decimal (10,2),
Discount Decimal (10,2),
[ship_Mode]Varchar (50),
Profit Decimal(10,2),
[Unit_Price]Decimal(10,2),
[Shipping_Cost]Decimal (10,2),
[Customer_Name] Varchar (255),
Province Varchar (100),
Region Nvarchar(100)
[Customer_segment] varchar (100),
[Product_Category]  varchar (100),
[product_sub_category]varchar (100),
[product_name]varchar (max),
[product_container] varchar(100),
[product_base margin] descimal(10,2)
[ship_date] date
)

---1
select product_category, sum([Sales]) as [Total sales]
from [dbo] .[KMS SQL case study]
group by product_category
order by [Total sales]desc

[dbo].[KMS SQL case study]
select * from [dbo].[KMS SQL case study]
CREATE DATABASE KULGAR_DB

----2
SELECT TOP 3 region,sum (sales) as [total sales]
from[dbo].[KMS SQL case study]
group by region
order by [total sales]desc


----3
select product_sub_category, sum(sales) as [total sales]
from  [dbo].[KMS SQL case study]
where region ='ontario'
group by product_sub_category


----4
select top 10 customer_Name, shipping_cost,sales, Discount, unit_price, sum(order_quantity) as [total order_quantity]
from[dbo].[KMS SQL case study]
group by customer_name,shipping_cost,sales,discount, unit_price
order by [total order_quantity]asc

----5
select Ship_mode, sum([shipping_cost]) as [total shipping_cost]
from [dbo].[KMS SQL case study]
group by ship_mode
order by [total shipping_cost]desc

----6
select customer_segment, product_sub_category,customer_name,sum(sales) as [Total sales]
from[dbo].[KMS SQL case study]
group by customer_segment, product_sub_category,customer_name
order by [total sales]desc


-----7
select top 1 *
from [dbo].[KMS SQL case study ]
where customer_segment ='small business'
order by sales desc

----8
select top 1*
from [dbo].[KMS SQL case study]
where customer_segment = 'corporate'
order by order_quantity desc

------9
select top 1*
from[dbo].[KMS SQL case study]
where customer_segment= 'consumer'
order by profit desc


-----10
select customer_name,customer_segment,product_category,product_sub_category
from[dbo].[KMS SQL case study]
join[dbo].[order_status]
on [dbo].[KMS SQL case study].order_ID=[dbo].[order_status].order_ID

-----11
SELECT 
"SHIP_MODE",
AVG("SHIPPING_COST") AS AVERAGESHIPPINGCOST
FROM 
[DBO].[KMS sql case study]
GROUP BY
"SHIP_MODE"
ORDER BY
AVERAGESHIPPINGCOST DESC;

 SELECT
 (ORDER_PRIORITY),
 (SHIP_MODE),
 COUNT(*)AS NUMBER_OF_ORDERS,
 SUM(SHIPPING_COST) AS
 TOTAL_SHIPPING_COST,
 AVG(SHIPPING_COST) AS AVG_SHIPPING
 FROM
 [KMS SQL CASE STUDY]
 GROUP BY
 (ORDER_PRIORITY),(SHIP_MODE)
ORDER BY
CASE (ORDER_PRIORITY)
WHEN 'CRITICAL' THEN 1
WHEN 'HIGH'  THEN 2
WHEN 'MEDIUM' THEN 3
WHEN 'LOW' THEN 4
ELSE 5
END,
SHIP_MODE;
 
