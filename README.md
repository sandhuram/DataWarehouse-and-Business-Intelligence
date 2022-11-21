# DataWarehouse-and-Business-Intelligence

Data-Warehousing-Business-Intelligence
Data Warehouse and Business Intelligence for Contoso Retail (ETL, Dimensional Modeling, Power BI, Tableau)

Overview
This project involves a retail company that sells a variety of products to people and to businesses across a variety of sales channels.

Project Overview

->Developed a data warehouse, pipelining data from diverse sources such as CSV, XML, MySQL, Postgres SQL and SQL Server using Talend Data Integration and SSIS.
->Designed star schema dimensional model on the data set, loading facts and dimensions.
->Implemented Error Handling, Load Statistics, Slowly Changing Dimensions, Currency Conversion and Performance Tuning.
->Built custom dashboards to analyze sales and customer segmentation using Tableau, Qlik Sense and PowerBI.
->This project involves a retail company that sells a variety of products to people and to business across variety of sales channels.

The Retail Company would like to:

->Creates a data warehouse (DW) from its various systems of records (SORs)
->Creates BI applications that enable analysis of business performance

The DW will store (Facts) in the following subject areas:
->Sales
->Inventory
->Sales Quota
->Strategy Plans

The Retail Company had the following products which were sold:
The categories of products sold: Audio TV and Video Computers Cameras and camcorders Cell phones Music, Movies and Audio Books Games and Toys Home Appliances The Retail Company would like to: Create a data warehouse (DW) from its various systems of record (SORs) Create BI applications that enable analysis of business performance

Observations in SOR
->Different unique key for product’s table across all SORs e.g. ProductID, BrandID, ProductLabel
->Length of the values were different across SORs
->Data type for dates in the CSV and TXT files are not constant.

DATA PROFILING:

->Changed the SOR Load and Update dates from TIMESTAMP to DATE for Oracle and PostgreSQL to load SOR_LOADDATE

->Converted data type values for DATES to DATE data type across all the CSVs and Text input files

->For SCDs DimProductPrice and DimProductCost we had to use SOR dimproduct (MySQL) as a bridge between input file price_cny_step_1_of_4 and DIMPRODUCT

->Converted all the possible columns in the target metadata from Big Decimal to INT

->Data Type csv contains all the column’s data type which we kept constant across all the SORs and Target table depending upon the size of data

->Had to append zeros and trimmed values in the for joining product tables

REJECT CODES AND ERROR HANDLING:

->Reject Codes are used to catch bad data,missing values or invalid data present in the facts rejects

->Reject Reasons help you understand the bad data in detail

->Handled null values using Relation.ISNULL function and applied code 99 if nulls are found

![image](https://user-images.githubusercontent.com/25193377/203154899-a9612bdb-9ec4-452b-b589-748de249461c.png)

CURRENCY CONVERSION:

![image](https://user-images.githubusercontent.com/25193377/203154955-64abfa1b-9f6d-4170-85da-ef2d62ac95eb.png)The company has 4 sales channels:

JOB SCREENSHOT:

![image](https://user-images.githubusercontent.com/25193377/203155086-a5f64c77-2866-4adc-9714-288a5018e9bd.png)

POWERBI Screenshot:

Sales Analysis:

![image](https://user-images.githubusercontent.com/25193377/203155173-770d5b57-b244-433b-8aaa-1eafc9394ba3.png)

![image](https://user-images.githubusercontent.com/25193377/203155217-ff757122-dbff-47a6-8a78-7adf6369c8aa.png)

![image](https://user-images.githubusercontent.com/25193377/203155238-204a1abe-ea93-49be-8702-b58a12365732.png)

![image](https://user-images.githubusercontent.com/25193377/203155263-d621d3b7-03a0-4abf-a719-ab4743bfc85f.png)

![image](https://user-images.githubusercontent.com/25193377/203155305-37b7a748-bc19-49a0-a1aa-23e435182304.png)

![image](https://user-images.githubusercontent.com/25193377/203155345-d42b728b-4fd0-4828-8a13-309701a6e797.png)

->Retail
->Stores
->Catalog
->Online

Three top-level geographic regions:

->North America
->Europe
->Asia

Customers who purchased products are tracked in :

->Catalog
->Online

Database	      Business Area	    dbms
Retail_SOR_NA	  North America	    Microsoft SQL Server
Retail_SOR_EU	  Europe	          MySQL
Retail_SOR_AS	  Asia	            PostgreSQL
Retail_SOR_CAT	Catalog	          Oracle
Flat Files	    Cross-unit        csv,text delimited
                reference data	

DW has dimensional model to support:

->Sales Analysis
->Inventory Analysis
->Sales quota & planning analysis

DI: Loading data sources into DW

->SOR: flat files, SQL Server, PostgreSQL, MySQL and Oracle
->DW: MySQL
->ETL: Talend

BI: Dashboards, Reports & Visualizations

->Inventory Analysis
->Sales quota & planning analysis

Deliverables - Analysis

1. Data Subjects
->Online Sales (FactOnlineSales)
->Sales (FactStoreSales)
->Inventory (FactInventory)
->Sales Quota
->Strategy Plan

2.Types of Analysis:

->Trending
->Ranking
->Comparison
->Period over Period
->Geo Map
->Contribution

3.Measures:

->Sales in $, Profit, Margin, Average order size,...

4.Dimensions:

->Customers: Company & Person, demographics
->Product: Product Hierarchy (Category, Subcategory, Product),Brand.
->Store: Type, Other attributes
->Dates
->Geography
