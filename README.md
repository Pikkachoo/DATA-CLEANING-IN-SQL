# Sales - Dashboard

### Dashboard Link : https://app.powerbi.com/links/k6qpoiEkun?ctid=c813a6bb-1f84-469b-9f80-df685f2f3f4f&pbi_source=linkShare
![image](https://github.com/Pikkachoo/Sales-data-analysis/assets/110214965/7931d45d-9311-4fe6-8b4c-17b302054a12)


## Project Overview

This analysis delved into sales data to identify trends, top-selling products, and revenue metrics for provide insights for business decision-making.

### Steps followed 

- Step 1 : The dataset is a csv file. I Uploaded the dataset using the 'Get Data' option in Power BI and then proceeded to transform the data.
- Step 2 : Identified the first row as headers and proceeded to promote headers by selecting 'use first row as headers' on the ribbon
- Step 3 : I navigated to the 'Transform' tab and select 'Detect Data Type' to automatically identify the data type of each column and convert them as needed.
- Step 4 : Split the datetime into date and time stamp.
- Step 5 : Created a new column with the DAX expression

  ```
          Month name =
          Table.AddColumn(#"Renamed Columns", "Month Name", each Date.MonthName([Month]*29))
  ```
  
- Step 6 : Created a visualization for Sales trend over time (x-axis=month name, y-axis=sum of sales) using the line chart.
- Step 7 : Ordered the months in chronological order by sorting them by month number in 'column tools'.
- Step 8 : Created a visualization for 'Best selling products' (category=product, values=count of sales) using tree map.
- Step 9 : Added another visual for 'Top 5 best selling product' (x-axis=sum of quantity ordered, y-axis=product) using stacked bar chart. 
- Step 10 : Created a visual for the Top 5 cities by sales using map. Loction field was set to 'city'.
- Step 11 : Visual filters (Slicers) were added for two fields named "City" and "Products".
- Step 12 : Three card visuals were added to the canvas. The first one representing total revenue generated, the second one was the sum of all the quantity ordered, and the third - profit margin. For creating thoses, the measure following DAX expression was written;
         ```
                REVENUE = SUM('Sales Data'[Sales])
                SALES QTY = SUM('Sales Data'[Quantity Ordered])
                PROFIT MARGIN = (([REVENUE]-[Total Cost])/[REVENUE])*100
         ```
Snap of new calculated column ,

![image](https://github.com/Pikkachoo/Sales-data-analysis/assets/110214965/85949f9a-58ab-47a5-b2d9-9a11ab8d561e)
