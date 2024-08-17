# Power_BI_Data_Modeling

## Scope of Work
The following objectives were achieved in the data analysis and modeling tasks.

**1) Sales Data Integration**: Various datasets, including sales data, product data, and others, were integrated and imported in the Model View from a SQL Database (MySQL Server). The initial task involved establishing relationships between these tables by identifying common columns for linking.

**2) One-to-Many Relationships**: One-to-many relationships were created between the tables to ensure accurate data aggregation and analysis. This process included mapping and implementing relationships based on shared attributes among the datasets.

**3) Snowflake Schema**: A snowflake schema was employed for the sales data to optimize the structure and improve query efficiency. This approach allowed for data normalization and better management of complex relationships among different entities.

<details><summary>Sales Model Schema</summary> 
<img src="https://github.com/user-attachments/assets/98b7282d-8b51-4749-b269-f2b52ad16ca3" alt="Sales Model Schema">
</details>

## Column Creation and Transformation - DAX 
Multiple columns were created using the Transform and Add Column functions in the Query Editor.

-- Calendar Table - creating columns  to capture temporal data such as start dates and other relevant time-based attributes
<details>
<summary>Click to view the image</summary>

<img src="https://github.com/user-attachments/assets/f7676d36-2ba9-483a-a04a-6debb2c7d4a1" alt="Descrizione dell'immagine" width="200" height="300">

</details>

-- Several Measures creation using DAX

A dedicated table was created to organize and manage the measures efficiently. This table facilitates the quick retrieval and application of measures, streamlining the overall data processing and analysis.

<details><summary>DAX Examples</summary>
  
a) 90-Day Rolling Profit = CALCULATE([Total Profit], DATESINPERIOD('Calendar Lookup'[Date], MAX('Calendar Lookup'[Date]), -90, DAY)) --> Calculates the total profit over the last 90 days.


b) % of All Returns = DIVIDE([Total Returns], [All Returns]) --> Calculates the percentage of total returns relative to all returns.


c) Bike Return Rate = CALCULATE([Return Rate], 'Product Categories Lookup'[CategoryName] = "Bikes") --> Calculates the return rate specifically for the "Bikes" category.


d) Profit Target = [Previous Month Profit] * 1.1 --> Sets a profit target as 110% of the previous month's profit.


e) YTD Revenue = CALCULATE([Total Revenue], DATESYTD('Calendar Lookup'[Date])) --> Calculates the year-to-date revenue using the newly created values from CC.
