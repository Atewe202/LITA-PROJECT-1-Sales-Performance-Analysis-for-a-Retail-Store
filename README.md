### LITA-PROJECT-1

### Project 1 Topic: Sales Performance Analysis for a Retail Store

### Summary of Porject
 This project is  aimed at analyzing the sales performance of a retail store.
2 The goal is to explore sales data provided to uncover key insights such as top-selling products, regional
performance, and monthly sales trends 
3 And to use Power BI dashboard to produce an interactive highlights from these findings.

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

### Data Cleaning
- Data cleaning was done in Excel by removing duplicated data
- Data cleaning was also done in Power BI by:
-  Transform data and
-  Then check data quality, Data profile and Data distribution

### Tools and Methods Used 
- Data Analysis: the data were analysed using the microsoft excel, pivot table to summarize the large data, organising them into tablees and use of slicers to filter.
- SQL queries was also used for further analysis ans
- Power BI for visualization of the collection


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
	Gloves		 200 
	Hat		 159 
	Jacket		 140 
	Shirt		 327 
	Shoes		 309 
	Socks		 122 
![image](https://github.com/user-attachments/assets/676a7794-b731-444f-af03-4ae630a1b235)



Shirt has highest average sales(327), followed by Shoes (309) and the least is Stocks -122


Total revenue by region: calculating the revenue per region using the formular =SUMIF(D2:D9922,"East",H2:H9922)
			
	Total Revenue by Region		
	East		 485,925 
	North		 387,000 
	South		 927,820 
	West		 300,345 
![image](https://github.com/user-attachments/assets/aa5aa178-e1ff-4ced-80a2-0c76ba0adad1)



- The highest revenue came from the South with a total of 927,820 with a percentage of 44% this was followed by the East with a revenue of 485,925 with a percentage of 23% and the least revenue came from the West with a total sales of 300,345 and percentage of 14%.

   Inghest inference
  

### Data Analysis

### Visulization



