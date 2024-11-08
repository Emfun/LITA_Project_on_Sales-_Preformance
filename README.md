# LITA_Project_on_Sales-_Preformance
This Analysis highligts the sales performance of a retail store

### Project Title: Sales Performanace Analysis 


### Project Overview 
The goal of this project is to analyze the sales data to better understand factors that drive revenue, identify growth opportunities and optimize sales strategies. By examining data collected over the years on product, region, customers and sales, this analysis aim to gain insights that will enhance decision-making and support sustained growth.



### Objectives 
- Assess overall sales performance 
- Identify top-performing products, 
- Regional breakdowns
- Generate actionable insight to inform future strategies



### Data Source: 
The source of data used is capstone dataset Sales.xlm.



### Tools Used
1. Microsoft Excel: Data Cleaning and Analysis
2. SQL Server Management Studio:  Querying data
3. Power BI: for Dashboard and Visualization



### Data Cleaning and Preparations
In this phase, the following action was taken
- Data loading and inspection
- Data cleaning and formatting



### Exploratory Data Analysis:
EDA was then carried out to answer the following
- Average sales per product 
- Total revenue by region



### Data Analysis
In this Phase the following lines of queries was used during the analysis

1. Retrieve the total sales for each product category.
```SQL
select PRODUCT, SUM(sales) as 'Total Sales'
from Sales_Data
group by Product
```

2. Find the number of sales transactions in each region.
 ```SQL
- select Region, count(sales) as 'Number of Sales' from Sales_Data
  group by Region
```

3. Find the highest-selling product by total sales value.
 ```SQL
select top 1 PRODUCT, SUM(sales) as 'Total Sales' from Sales_Data
group by Product order by sum(sales) desc
```
4. Calculate total revenue per product.
 ```SQL
select product, SUM(sales) as Total_revenue from Sales_Data
group by Product
```
5. Calculate monthly sales totals for the current year.
```SQL
select datename(MONTH, OrderDate) as MonthNames, SUM(Sales) as Monthly_Total
from [dbo].[Sales_Data]
where YEAR(OrderDate) = YEAR(GETDATE())
group by Datename(MONTH, OrderDate)
order by MonthNames	
```
6. Find the top 5 customers by total purchase amount.
```SQL
select top 5 customer_id, sum(Sales) as Total_purchase from [dbo].[Sales_Data]
group by Customer_Id
order by Total_purchase desc
```



### Data Visualization:
In this Phase a Dashboard that shows the Sale Performance was created using the Power BI tool

![Performance Dashboard](https://github.com/user-attachments/assets/36284491-327d-41a3-bffe-4447d31668b0)


### Conclusion
W

