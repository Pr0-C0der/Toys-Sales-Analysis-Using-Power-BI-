# Toys Sales Analysis Using Power BI
Developing an interactive dashboard for a toy company, "Maven Toys". Managers can use this dashboard to get comprehensive report about the sales of toys.
The aim of this data analysis project is to create an interactive dashboard using Power BI for analyzing sales of a toy company called "Maven Toys". The project involves taking raw sales and inventory data, cleaning and transforming it into a suitable format, and then visualizing the insights through an interactive and user-friendly dashboard.

# Overview
We have been given data about the sales, products, inventory and stores in CSV format. The data describes the 820,000+ transactions for all Maven Toys stores. The data spans from January 1st 2017 to September 30th 2018.

The main questions that are require to be answered are:
1. Which product categories drive the biggest profits? Is this the same across store locations?
2. Can you find any seasonal trends or patterns in the sales data?
3. Are sales being lost with out-of-stock products at certain locations?
4. How much money is tied up in inventory at the toy stores? How long will it last?

# Data Collection and Description:
The data is collected from [Maven Data Playground](https://www.mavenanalytics.io/data-playground).

We are given four files in CSV format described below:

### Products:
1. Product_ID - ID of the Product
2. Product_Name - Name of the Product
3. Product_Category - Category of Product
4. Product_Cost - Product Cost (USD)
5. Product_Price - Retail Price (USD) 

### Sales:
1. Sale_ID - Sale ID for each transaction 
2. Date - Date when the transaction occured
3. Store_ID - Unique ID given to toy store
4. Product_ID - ID of the Product
5. Units - Units of product sold

### Stores:
1. Store_ID - Unique ID given to toy store
2. Store_Name - Store Name given of each toy store
3. Store_City - City where the store is located
4. Store_Location - Area where the store is located (Downtown,Commercial, Residential, Airport)
Store_Open_Date - Store Opening Date

### Inventory:
1. Store_ID - Unique ID given to toy store
2. Product_ID - ID of the Product
3. Stock_On_Hand - Units of products currently in the inventory

# Data Cleaning and Preparation:
The process is described as follows:
1. Import files in Power BI. 
2. Remove Duplicate Rows from all the files.
3. Since, all the Product_Cost and Product_Price are in text format, we convert them into integers.
4. We connect the different files using respective Primary and Foreign Keys: <br />
![image](https://github.com/Pr0-C0der/Toys-Sales-Analysis-Using-Power-BI-/assets/93116210/7ca4e022-8180-4114-90ba-4d2784605743)

6. For the purpose of displaying the cities where the stores are located on a map, we create new coloumn indicating the full address of the city. The format is: <br /> Store_City + ", Mexico".
7. To analyze the inventory, we add new coloumn depicting the inventory sales and inventory profit. <br /> 
The Inventory Sales is calculated by: Inventory Sales = Stock_On_Hand * Product_Price <br />
The Inventory Profit is calculated by: Inventory Sales = Stock_On_Hand * (Product_Price - Product_Cost) <br />

7. Since, one of the major factors that management trys to look at is Total Cost of creating the products and the Total Retail and Profit, to calculate it we add a new coloumns in the named Total Cost, Total Retail and Profit in the sales file. <br />
The total cost is calculated by: Total Cost = (Units) * (Product Cost) <br />
The total price is calculated by: Total Retail = (Units) * (Product Price) <br />
We also calculate the Profit by: Profit = Total Retail - Total Cost <br />

# Data Analysis:
Considering the questions that we are required to answer, We create an interactive dashboard for analyzing the sales and inventory data. The user is given options to analyze the data related to a particular store, city, product or timeline. This helps him/her to get a comprehensive report of the performance of the company.

### Sales Analysis Dashboard
![Sales Dashboard](https://github.com/Pr0-C0der/Toys-Sales-Analysis-Using-Power-BI-/assets/93116210/c1785a3c-3f36-4de5-85e5-c80911fbcd5f)

### Inventory Analysis Dashboard
![Inventory Dashboard](https://github.com/Pr0-C0der/Toys-Sales-Analysis-Using-Power-BI-/assets/93116210/336f1a1d-7b6f-4762-b27f-f6dc48863290)

# Answering the Questions:
### 1. Which product categories drive the biggest profits? Is this the same across store locations?
From the Sales Dashboard, we can clearly see that the product categories that give the biggest profits are, **_Toys_** and **_Electronics_**. <br />
These categories provide a total profit of **_1 Million$ +_**.
**_Toys_** and **_Electronics_** continue to be the product categories that drive the biggest profits, across store locations. <br />

### 2. Are there any seasonal trends or patterns in the sales data?
The seasonal trends observed are:
1. From **_January 2017_** to **_April 2017_** there is **_increase_** in sales from $542,554 to $681,072.
2. **_Decline_** of sales from **_April 2017_** to **_August 2017_** from $681,072 to $489,422.
3. Steady **_increase_** of sales from **_August 2017_** to **_December 2017_** from $489,422 to $877,203.
4. The highest sales are recorded in month of **_December_** ($877,203). Maybe because of Christmas. 
5. The **_Toys category_** has showed a **_stable demand_** but the demand for **_Electronics_** are **_decreasing steadily_** . Hence, it is advised that company invest more in the Toys Category.
6. The **_Art and Crafts category_** has shown **_substantial growth_** in sales from **_January 2017_** to **_September 2018_** . Maven Toys may benefit from this increased demand.

### 3. Are sales being lost with out-of-stock products at certain locations?
**_From Analysis, we can conclude that offering of additional products does not have a significant impact on sales as their demand is less in the market._** <br />
Contrary to popular belief, not all products will necessarily sell more in stores that carry them all. **_40% of the 50 stores had no more than 30 products to offer._**
**_Stores are refraining from keeping less demand products in their store._**

### 4. How much money is tied up in inventory at the toy stores? How long will it last?
**_There are 29,742 units of products available currently in all stores. However, this quantity is not sufficient to meet the monthly demand of customers._** <br />
We should expect 410k$ in sales across all its stores. **_The average number of units sold has risen despite a decline in sales over the last three months._** The demand in the upcoming three months is probably going to be higher than the monthly average of units sold, going by past trends. **_To meet the demand at the end of the year, Maven Toys will need to aquire more than its monthly average._**
