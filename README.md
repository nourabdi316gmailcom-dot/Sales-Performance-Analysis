Sales Performance Analysis 

Project Overview

This project analyzes sales performance using Microsoft Power BI.
The interactive dashboard helps users explore sales, profitability,
monthly trends, product categories, geographic regions, and customer
segments.

Objectives

• Monitor key sales performance indicators.
• Explore monthly sales trends.
• Compare sales across product categories and regions.
• Understand sales contributions from customer segments.
• Use interactive slicers to filter the analysis by year, category,
region, and customer segment.

Tools and Technologies

• Power BI Desktop — data modeling and dashboard development
• Power Query Editor — data cleaning and transformation
• DAX — measures and calculations
• Excel/CSV — source data, as applicable to the dataset used

Data Preparation

The data preparation process included reviewing data types, handling
inconsistent date formats, and creating a corrected date field
(OrderDateFixed) for date-based analysis. Data quality checks should
be completed for remaining missing values, conversion errors, duplicate
records, and invalid numeric values.

Data Model

The intended model uses a star-schema structure:

• FactSales — transaction-level sales data and numeric measures
• DimCustomer — customer name, gender, and customer segment
• DimProduct — product name and category
• DimLocation — city and region
• DimDate — date, year, month, quarter, and year-month

Dimension tables should have unique keys, and relationships should be
active and correctly configured. The location key should match between
FactSales and DimLocation.

DAX Measures

The dashboard includes KPI measures for total sales, total profit,
profit margin, and total orders. Example formulas (adjust column names
if your model uses different names):

Total Sales = SUM(FactSales[SalesAmount])

Total Cost = SUM(FactSales[CostAmount])

Total Profit = [Total Sales] - [Total Cost]

Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)

Total Orders = DISTINCTCOUNT(FactSales[OrderID])

Format Profit Margin as a percentage if the measure returns a decimal
ratio (for example, 0.31 displays as 31%).

Dashboard Features

• KPI cards for key performance indicators
• Line chart showing total sales by month
• Bar chart comparing total sales by product category
• Chart comparing total sales by region
• Donut chart showing sales by customer segment
• Interactive slicers for Year, Customer Segment, Category, and Region

Initial Observations

The dashboard screenshot displays approximately 12.23M in Total
Sales and 3.75M in Total Profit. The margin card displays 0.31;
if the measure is a decimal ratio, format it as 31% for readability.
The dashboard also indicates differences across categories, regions, and
customer segments. Confirm detailed rankings and explanations from the
underlying data before publishing specific business conclusions.

Recommendations

• Verify that all KPI titles match their measures.
• Confirm that the profit margin is formatted correctly.
• Ensure month values are sorted chronologically, especially if the
dataset contains multiple years.
• Use slicers to investigate differences across categories, regions,
and customer segments.
• Investigate lower-performing categories or regions before
recommending business actions.
• Validate model relationships and reconcile key totals against the
source data.

Limitations

• Findings should be validated against the underlying dataset.
• The dashboard screenshot alone does not establish the causes of
sales differences.
• Remove or anonymize personal or sensitive customer information
before sharing data files.

How to View the Project

1. Download or clone this repository.
2. Open the .pbix file using Power BI Desktop.
3. Refresh the data only if the source files and required paths are
available.
4. Use the slicers to explore the dashboard.


Noura Abdilahi
Data Analytics Portfolio Project