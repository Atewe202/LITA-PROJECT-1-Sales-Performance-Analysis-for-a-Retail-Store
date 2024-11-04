### LITA-PROJECT-1

### Project 1 Topic: Sales Performance Analysis for a Retail Store

### Summary of Porject
- This project is  aimed at analyzing the sales performance of a retail store.
- The goal is to explore sales data provided to uncover key insights such as top-selling products, regional
performance, and monthly sales trends 
- And to use Power BI dashboard to produce an interactive highlights from these findings.

### Objective of the Project
The project was designed to address the following goal using thee stipulated tools
1. Excel
  - Perform an initial exploration of the sales data. Use pivot tables to summarize 
  - total sales by product, region, and month.
  - Use Excel formulas to calculate metrics such as average sales per product and 
  - total revenue by region.
  - Create any other interesting report

2. SQL
Write queries to extract key insights based on the following questions. 
  - retrieve the total sales for each product category.
  - find the number of sales transactions in each region.
  - find the highest-selling product by total sales value.
  - calculate total revenue per product.
  - calculate monthly sales totals for the current year.
  - find the top 5 customers by total purchase amount.
  - calculate the percentage of total sales contributed by each region.
  - dentify products with no sales in the last quarter.

3. Power BI:
  - Create a dashboard that visualizes the insights found in Excel and SQL.
  -  The dashboard should include a sales overview, top-performing products, and 
  regional breakdowns.

### Data Source
The dataset include the following key columns
- OrderId; Which is a unique identifier assigned to a specific order in the retail store
- CustomerId: which is also a unique identifier assigned to each customer within the retail store
- Product: This refers to the items offered for sale to customers in the retail store
- Region: The geographical area
- Quantity: The total amount of product sold
- Unit price: Cost of a single unit of product
- Revenue: Income generated from sales of products

### Tools Used
The data was anlysed using 
1. MicrosoftExcel by performing the following functions 
- Creating the column for Totalsale = quantity * Unitprice
- Use of Pivot table to organise and  summarise the findings gained insights
- Creating an Excel dashboard which is a visual (charts, line graphs) reporting tool that display key daatpoints and metrics in a concise, interactive and easy to read format
-   Use of slicer aaqn interactive tool that allows to filter and view  specific parts of data dynamically
2. SQL- Structured Query Language which is
-  A programming language used to manage and maneipulate rational database.
-  It was used for Aggregating, summaarizing and Performing calculaations on data insights
 3. Power BI which is a busness analytics tool by microsoft that enables users to
  - Connect to data sources
  - Transfform 
 - Model data and
 - Createe interactive visually appealing dashboards and reports 

### Data Cleaning and Preparation
- Data cleaning was done in Excel by removing duplicated data
- Get data was used to get the data from Excel work book in Power BI and data was transformed 
-  Data cleaning was also done to remove duplicates:
-  Then check column quality, column profile and column distribution

### Tools and Methods Used 
- Data Analysis: the data were analysed using the microsoft excel, pivot table to summarize the large data, organising them into tablees and use of slicers to filter.
- SQL queries was also used for further analysis ans
- Power BI for visualization. Tool used were bar charts, tables, donut and pie charts.
- -Slicer was used to filter


### Data Analysis 
### Calculated Metrics
 Use Excel formulas to calculate metrics such as;
 - Average sales per product : calculating the Average sales per product using the formula =AVERAGEIF(C2:C9922,"Gloves",H2:H9922)
 - Total revenue by region: calculating the revenue per region using the formular =SUMIF(D2:D9922,"East",H2:H9922)
### Queries used in SQL
find the highest-selling product by total sales value. SELECT Product, SUM(SALES) AS TOTALSALES FROM [dbo].[LITA_SALES_DATA]
GROUP BY PRODUCT
ORDER BY TOTALSALES DESC
  - calculate total revenue per product. using pivot table. this was done by grouping the product by the revenue generated. Shoes top the sales by generating 613,380 which has an overall percentage of 29% of the total sales, this was followed by shirt with a total revenue of 485,600 and percentage of total revenue of 23%, however the least revenue came from stocks 185,789 with a percentage of 9% of the total revenue.
  - Insight inference
    the high sellling products should be optimized, increase production and expand product line.
    - For the least selling product the is need to do a svrvey to find out why the poor sales. Inaddition the company can rebrand it or review the unitprice.. the last option could be to discontinue product if all other strategies fail
SELECT Product, SUM(SALES) AS TOTALREVENUE FROM [dbo].[LITA_SALES_DATA]
GROUP BY PRODUCT
  - calculate monthly sales totals for the current year. 
SELECT OrderDate, SUM(SALES) AS MONTHLYSALES FROM [dbo].[LITA_SALES_DATA]
WHERE OrderDate BETWEEN '2024-01-01' AND '2024-12-31'
GROUP BY OrderDate
ORDER BY Monthlysales DESC
  - find the top 5 customers by total purchase amount. SELECT TOP 5 Customer_Id, SUM(SALES) AS TOTALPURCHASE FROM [dbo].[LITA_SALES_DATA]
GROUP BY Customer_Id
ORDER BY TOTALPURCHASE DESC
  - calculate the percentage of total sales contributed by each region. SELECT REGION, SUM(Sales) AS SalesPerRegion, (SUM(Sales) * 100 / (SELECT SUM(SALES) FROM [dbo].[LITA_SALES_DATA]))
 AS SALESPERCENTAGE FROM [dbo].[LITA_SALES_DATA]
 GROUP BY REGION
 ORDER BY SALESPERCENTAGE DESC

  - dentify products with no sales in the last quarter. SELECT Product FROM [dbo].[LITA_SALES_DATA]
GROUP BY PRODUCT
HAVING MAX(OrderDate) < DATEADD(QUARTER, -1, GETDATE());


### Explaratory Data Analysis
Average sales per product : calculating the Average sales per product using the formula =AVERAGEIF(C2:C9922,"Gloves",H2:H9922) 	Average Sales by Product		

![Screenshot 2024-10-31 130309](https://github.com/user-attachments/assets/abc9a7cf-3c9b-4337-b89c-135534b420bf)

![Screenshot 2024-10-31 120511](https://github.com/user-attachments/assets/350f4dee-374e-4eb6-bd7b-ba7e9c0f2d18)


Shirt has highest average sales(327), followed by Shoes (309) and the least is Stocks -122

Total revenue by region: calculating the revenue per region using the formular =SUMIF(D2:D9922,"East",H2:H9922)
			
![image](https://github.com/user-attachments/assets/aa5aa178-e1ff-4ced-80a2-0c76ba0adad1)

![Screenshot 2024-10-31 111657](https://github.com/user-attachments/assets/51ea53fd-2d60-418f-85de-08a07b93c4a9)

- The highest revenue came from the South with a total of 927,820 with a percentage of 44% this was followed by the East with a revenue of 485,925 with a percentage of 23% and the least revenue came from the West with a total sales of 300,345 and percentage of 14%.

### Insighest inference
 -  The high revenu generated by the south region is an indication of the strong market presence and are likely to have a large and loyal customers. the products could also be said to have gained ground/acceptance in the south region.
 -  However expanding product offerings or increasing market efforts could further help to capitalize on the region potential.
-  For the region with the lowest sales there may be need to re-evaluate performance, market strategy, also consider regional differences that could afeect customers behaviourx.
-  Inaddition other market conditions that may be affecting sales should be considered.
-  The company could also look at the highest selling product in that region and concentrate more effort in reaching more customers.

Total revenue by Month: 
Insights
- An anlysis of the total revenue per month shows that February has the highest sales
- The highest reveneue was recorded in the month of february  with a percentage of 26% , followed by July with percentage of 13%, January with a percentage of 12% and June. with percentage of 12%
- The least sales was recorded in Sepember and December with a percentage of 2% each .
- This seasonal trends could be due to fluctuations in customers demand and the prevailing economic situation
  Inference
- However there is need to optimize marketing strategies to capitalize peak seasons
- There is also need to develop targeted promotions for loe level months
- Adjust resource allocation to match demend fluctuations.
  
![Screenshot 2024-10-31 132618](https://github.com/user-attachments/assets/3c1610cf-2497-4b5e-b970-777ab5c1e913)

![Screenshot 2024-10-31 133529](https://github.com/user-attachments/assets/c6358249-73ab-4e6f-a322-95afc960ef10)

 Monthly Sales by Current Year:
 Insight
-  This analysis shows no consistent trend in the revenue generated in the current year per month. 
- This seasonal trends could be due to fluctuations in customers demand and the prevailing economic situation

  Inference
-  There is need to optimize marketing strategies to capitalize peak seasons
- There is also need to develop targeted promotions for loe level months
- Adjust resource allocation to match demend fluctuations.
  
![Screenshot 2024-10-31 143954](https://github.com/user-attachments/assets/c5733fad-143e-493f-8dee-6149b5010b75)

Top 10 Customers by Total Purchase
Insight
- This analysis shows the top ten customers purcahsed products worth 4,235. 
- There is a need to also see how to increase the purchasing power of other customers by x-raying their products of choice
- This could be done by conducting a customer satisfaction survey to identify areas of improvement

  Inference
  - Top customer can be assigned a dedicated paypoint which will also encourage some customer to want to increase their purchasing level
  - Offer regular programs or premium services which serves as incentives to them
  - After sales relationship can be encouraged where them receive messages during their birthdays, festive periods
     

![Screenshot 2024-10-31 145224](https://github.com/user-attachments/assets/8c0bbe7e-b985-4c2a-92a2-d7c730fe619b)

### Percentage contributed by different Regions


![Screenshot 2024-10-31 154546](https://github.com/user-attachments/assets/154f4f00-4742-4f0e-bc16-532e95b973eb)


### Visulization

![Screenshot 2024-11-01 125157](https://github.com/user-attachments/assets/18289fc1-3610-43db-9205-55aa2b52c90f)

![Screenshot 2024-11-01 151744](https://github.com/user-attachments/assets/c3891816-8860-4520-9643-0577a67f9eef)


This dashboard shows insights of total revenue of 2,101,090  generated from 33,787 customers
- This report shows the Sales of 6 products (Hats, Gloves, Jacket, Shirts, Shoes and Stocks) by Region (East, North, South and West) highlighting the Revenue generated by Product, Region and by month
- Analysis of total revenue by product  shows that the top performing product is shoes with a total revenue of 613,380 (29%) while the least is stocke with a revemue of 180,785 (8%).
- Slicer was used to breakdown performance by region with the South being the  top performing region with a of 927,820 (44) and the least revenue was generated from the west 300,345 (14%) .
- This also revealed the product that top the sales which is shoes, followed by shirt and the least is stocks.
- In the month by revenue and product analysis February top performance and least in September 
- This seasonal trends could be due to fluctuations in customers demand and the prevailing economic situation
  Inference
- However there is need to optimize marketing strategies to capitalize peak seasons
- There is also need to develop targeted promotions for loe level months
- Adjust resource allocation to match demend fluctuations.
  
  ### Recommendations
  The following are some of the recommendations
   1. Market campaigns should be optimised
   2. Increased production of high selling products in different regions
   3. Expand product line
   4. Discontinue rebranding of products not doing well
   5. Prices can also be reviewed to win customers
   6. Market saturation should also be analysed
   7. Customer feedback is key to identify area of improvement

  ### Conclusion
 The south region should be strenthened to optimize performance. They should expand product line of high performing products -shoes and shirts.
 Stocks should be rebranded, provided incentives and also expand the market in the region where there is high demend in the South and the West
