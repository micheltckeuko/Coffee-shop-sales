# Coffee shop sales

## Project overview
This project aims to provide actionable insights to the new CEO of Bright Coffee Shop by analyzing historical sales transactions. The analysis focuses on identifying revenue-driving products, peak sales hours, product performance trends, and recommendations to optimize sales strategies.

### Data sources
Bright Coffee Shop Sales Data: the dataset used for this analysis is the "Bright Coffee Shop Sales.xlsx" file, containing detailed information about each sale made by customer.

### TOOLS
- EXCELS - Data cleaning
- SQL SNOWFLAKE- DATA Analysis
- POWER point  - for presentation

### Data Cleaning/ Preparation
In the Data preparation phase, we perform the following tasks:
1. convert dataset  from Excel file to Csv file.
2. Data loading and Inpection.
3. data cleanin and formating.
   
### Exploratory Data Analysis
EDA involve exploring the sales data to ascwer key question, such as:

- During which time intervals does the coffee shop experience the highest transaction volume?
- Which product types generated the highest total revenue over the analysis period?
- Which product categories have the highest number of units sold?
- What are the top 4 products by total revenue?

### Data Analysis
code  that I worked with
```sql
SELECT*, COUNT(PRODUCT_ID) AS PRODUCT_SOLD, 
SUM(TRANSACTION_QTY*UNIT_PRICE) AS TOTAL_AMOUNT, 
COUNT(TRANSACTION_ID) AS NUMBER_of_sales,
to_char(TO_DATE(TRANSACTION_DATE, 'YYYY/MM/DD'), 'YYYYMM') AS MONTH_ID,
CASE
 WHEN TRANSACTION_TIME BETWEEN '06:00:00' AND '11:59:59' THEN 'MORNING'
 WHEN TRANSACTION_TIME BETWEEN '12:00:00' AND '15:59:59' THEN 'AFTERNOON'
 WHEN TRANSACTION_TIME BETWEEN '16:00:00' AND '18:59:59' THEN 'EVENING'
 ELSE 'NIGHT'
 END AS TRANSACTION_TIME_BUCKET
FROM
  BRIGHTLIGHTCOFFEE.PUBLIC.COFFEESHOP_SALES
group by all;
```
### Results/ Findings  


