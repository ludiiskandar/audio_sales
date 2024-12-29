# Audio Sales Analysis

---
## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Recommendations](#recommendations)

---
### Project Overview

This data analysis project aims to provide insights into the sales performance of an Audio company over the past year. By analyzing various aspects of the sales data, I seek to identify trends, make data-driven recommendations, and gain a deeper understanding of the company's performance.

![audio_sales_report-1](https://github.com/user-attachments/assets/f2ca4085-a255-4681-94bc-dc13b207cf98)

[audio_sales_report.pdf](https://github.com/user-attachments/files/18268331/audio_sales_report.pdf)

---
### Data Sources

Sales Data: The primary dataset used for this analysis is the "audio_sales.zip" file, containing detailed information about each sale made by the company.

---
### Tools
- SQL Server Management System - Data Analysis
- PowerBI - Creating reports

---
### Exploratory Data Analysis
EDA involved exploring the sales data to answer key questions, such as:

- What is the overall sales trend?
- Revenue by Country?
- Revenue by date and year?
- Which products are top sellers?
- What are the peak sales periods?
- Detail table view.

---
### Data Analysis
Include some interesting code/features worked with

```sql
WITH cte as
(SELECT
a.Product_ID,
a.Product,
a.Brand,
a.Category,
a.Description,
a.Sale_Price,
a.Cost_Price,
a.Image_url,
b.Customer_Type,
b.Country,
b.Date, 
b.Units_Sold,
b.Discount_Band,
(Sale_Price*Units_Sold) AS revenue,
(Cost_price*Units_sold) AS total_cost,
format(date,'MMMM') AS month,
format(date,'yyyy') AS year
FROM product_data  a
JOIN product_sales b
ON a.Product_ID = b.Product)


SELECT *,
(1-Discount*1.0/100)*revenue AS  discount_revenue
FROM cte c
JOIN discount_data d
ON c.Discount_Band = d.Discount_Band AND c.month = d.Month
```

---
### Connecting Database to Power BI

connecting data base from sql to power BI

---
### Results/Findings
The analysis results are summarized as follows:
1. Customer type of Government made the highest revenue and profit for audio company.
2. Product Category A is the best-performing category in terms of sales and revenue.
3. Customer segments with high lifetime value (LTV) should be targeted for marketing efforts especially for small business and enterprises.

---
### Recommendations
Based on the analysis, we recommend the following actions:
- Invest in marketing and promotions during peak sales seasons to maximize revenue.
- Focus on expanding and promoting products for customer category small business and enterprises.
- Implement a customer segmentation strategy to target high-LTV customers effectively.

---
### Limitations
I had to remove all zero values from budget and revenue columns because they would have affected the accuracy of my conclusions from the analysis. There are still a few outliers even after the omissions

---
### References
1. SQL for data analysis
2. (https://stack.com)](https://github.com/Gaelim/youtube/blob/master/Data%20Analysis%20Project%20November%202024%20-%20Copy.zip)

😄

💻

|Heading1|Heading2|
|--------|--------|
|Content|Content2|
|PowerBI|SQL|

`column_1`

