# Coffee shop sales

## Project overview
This project aims to provide actionable insights to the new CEO of Bright Coffee Shop by analyzing historical sales transactions. The analysis focuses on identifying revenue-driving products, peak sales hours, product performance trends, and recommendations to optimize sales strategies.

### Data sources
Bright Coffee Shop Sales Data: the dataset used for this analysis is the "Bright Coffee Shop Sales.xlsx" file, containing detailed information about each sale made by customer.

### Tools
- EXCELS - Data cleaning.
- SQL SNOWFLAKE- DATA Analysis.
- Pivot table for Data visualisation.

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
- Barista Espresso is the top revenue generator (91k).
- Brewed  Chai Tea (80K) and Hot Chocolate are strong performers.
- Coffee leads with the highest item quantity sold ( 89,25k). 
- Tea follows as the second most sold category (697k).
- Sales peak: morning time  the top-selling time.
- A drop occurs after 11 AM, and revenue remains steady but lower from 12 PM to 5 PM.
- Sustainably Grown Organic Lg(21151.75k) and Dark Chocolate Lg  (21006K)are the top revenue generators.
### Recommendations
Based on the analysis, we recommend the following actions:
- Encourage mix-product to help boost other product.
- Focus inventory and promotions on Coffee and Tea — the top best.
- Stock heavily during morning period  best time to make good profits.
- Focus marketing on organic and chocolate product lines to drive revenue.

  ### Excel/ Pivot table: Data visualisation
  ![image](https://github.com/user-attachments/assets/146979b6-d995-4e94-9934-0e529b6fc545)
  ![image](https://github.com/user-attachments/assets/b3f67da8-2568-4858-ab1c-8c6c9eec53c9) 
![image](https://github.com/user-attachments/assets/1f691576-5658-4920-8c79-18f3660dabf2) 
![image](https://github.com/user-attachments/assets/07015f10-9cc3-4b4f-9bd2-456df7c99fb8)









