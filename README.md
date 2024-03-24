# Sales-Insights-using-Power-BI-and-MySQL

### Dashboard Link : https://app.powerbi.com/groups/me/reports/1785d395-f8cb-46b7-8658-dfef9c4941b6/ReportSection?experience=power-bi
## Problem Statement

This dashboard helps the computer hardware company to understand their sales. It helps the company understand their revenue trend and quantity they sold in a span of 4 years. By getting to their revenue, sales, profit contribution percentage on different regions throught the country, they can identify means to improve their sales and profit. It also lets them know which region contributes the most in their profit percentage and also who are the top clients based on revenue on the span of four years.

Since, the overall sales quantity in the year 2018 (997K) is greater compared to the year 2020 (350K), the company must work on improving their sales

Moreover, since the overall profit percentage by market is almost -21% in Bengal, they must try to reduce the loss.


### Steps followed 

- Step 1 : The data was in MySQL database and the SQL database was connected to Power BI. There are totally 5 tables (Customers, Date, Markets, Products, and Transaction) present within this database.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : We create a Entity Relationship Diagram (ERD). The snap of the diagram is below,
![Img_1](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/8b5f878f-6642-4592-bd14-012762033f3c) 
- Step 5 : In the markets table it was observed that we had market names outside of India, since we are focusing only on the Indian market, we removed non-Indian market names 
- Step 6 : In the transaction table the sales amount column had '0' and '-1' values present in them, so we remove all those rows with sales_amount <= 0.
- Step 7 : Next, we normalize all the sales_amount by adding a new column called normalized_sales_amount and convert the currency to INR. 
- Step 8 : In the dashboard view we create a new table by clicking on 'Enter Data' and name the table as 'Base measure'. This base measure will be our revenue, and the DAX expression is shown below,

        Revenue = SUM('sales transactions'[sales_amount])
A card visual is used to represent the revenue.
![Img_2](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/092a0d5a-778d-4383-8cf9-04b5e469c2f5)
- Step 9 : Similarly we do the same thing to find the sales quantity.

The DAX expression to find the sales quqntity is, 

        Sales Qty = SUM('sales transactions'[sales_qty])
A card visual is used to represent the Sales Quantity.
![Img_3](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/cc61cc05-010f-4954-9bad-874a2dba0a85)
This provides us with the overall sales amount which is the Revenue and Sales Quantity for all years.
- Step 10 : In the next step, we create bar chart for revenue across different market and sales quantity across different market.
- Step 11 : We also create line chart to show the revenue trend from 2017 to 2020.
The visual is shown below,
![Img_4](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/d94b7bf4-3187-446b-a87b-e567bb530e76)

- Step 12 : Since the company works by selling computer hardware to customers, we create a pie chart to find the top 5 customers and a bar chart to find the top 5 products.

The pie chart visual for Top 5 customers is shown below,
![Img_5](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/88c21552-879c-4b66-9d3f-a688dc5c3605)

The bar chart visual of top 5 products is shown below,
![Img_6](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/b03062b1-c096-4e7e-a5c5-4dc2fdaf3e0f)

- Step 13 : In the second page of the dashboard, we create a card view of Toal profit margin along with revenue and sales quantity by creating a table. The DAX expression is below,

        Total Proft Margin = SUM('sales transactions'[Profit_margin])
- Step 14 : We create a line chart to visualizae the profit margin trend from 2017 to 2020.

The line chart for profit margin trend is below,

![Img_7](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/13a129dd-5821-4111-8d79-ffef0341f486)
        
- Step 15 : Finally, to get a more detailed understanding, we also create a table with customer_name, revenue, revenue_contribution %, profit_margin_contribution %, and profit_margin %.

The table view is given below,

![Img_8](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/3b2f58ad-ca2c-4c24-a8c7-6e787ccb4e3d)
 
 - Step 16 : The report was then published to Power BI Service.

# Snapshot of Dashboard (Page-1)

![Img_9](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/fb97dcd5-f46e-437f-b092-0d09fb471fd6)

 
 # Report Snapshot (Page-2)

 
![Img_10](https://github.com/Shanmugam04/Sales-Insights-using-Power-BI-and-MySQL/assets/49804271/a3ed6920-3b35-4236-8618-8bb71d466913)
