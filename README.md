# DataWarehouse-and-Business-Intelligence

Data-Warehousing-Business-Intelligence
Data Warehouse and Business Intelligence for Contoso Retail (ETL, Dimensional Modeling, Power BI, Tableau)

Objective
Developed Multi-Dimensional data model (STAR Schema) and enhanced it to meet growing requirements.
Created a centralized data warehouse, pipelining retail data from diverse data sources using Talend Implemented Slowly Changing Dimensions, Rejection codes, and Performance tuning on a dataset with 48 million rows.
Built interactive dashboards to convey stories of retail sales and customer segmentation using Tableau and PowerBI.
Overview
This project involves a retail company that sells a variety of products to people and to businesses across a variety of sales channels.

The Retail Company would like to: Create a data warehouse (DW) from its various systems of record (SORs) Create BI applications that enable analysis of business performance

The DW will store (facts) in the following subject areas: Sales Inventory Sales Quotas Strategy Plans

Retail
The categories of products sold: Audio TV and Video Computers Cameras and camcorders Cell phones Music, Movies and Audio Books Games and Toys Home Appliances The Retail Company would like to: Create a data warehouse (DW) from its various systems of record (SORs) Create BI applications that enable analysis of business performance

Observations in SOR
Different unique key for product’s table across all SORs e.g. ProductID, BrandID, ProductLabel
Length of the values were different across SORs
Data type for dates in the CSV and TXT files are not constant.
Data Profiling
Changed the SOR Load and Update dates from TIMESTAMP to DATE for Oracle and PostgreSQL to load SOR_LOADDATE
Converted data type values for DATES to DATE data type across all the CSVs and Text input files
For SCDs DimProductPrice and DimProductCost we had to use SOR dimproduct (MySQL) as a bridge between input file price_cny_step_1_of_4 and DIMPRODUCT
Converted all the possible columns in the target metadata from Big Decimal to INT
Data Type csv contains all the column’s data type which we kept constant across all the SORs and Target table depending upon the size of data
Had to append zeros and trimmed values in the for joining product tables
Reject Codes and Error Handling
Reject Codes are used to catch bad data,missing values or invalid data present in the facts rejects
Reject Reasons help you understand the bad data in detail
Handled null values using Relation.ISNULL function and applied code 99 if nulls are found

Project Overview
Developed a data warehouse, pipelining data from diverse sources such as CSV, XML, MySQL, Postgres SQL and SQL Server using Talend Data Integration and SSIS.
Designed star schema dimensional model on the data set, loading facts and dimensions.
Implemented Error Handling, Load Statistics, Slowly Changing Dimensions, Currency Conversion and Performance Tuning.
Built custom dashboards to analyze sales and customer segmentation using Tableau, Qlik Sense and PowerBI.
This project involves a retail company that sells a variety of products to people and to business across variety of sales channels.
The retail company:
Creates a data warehouse (DW) from its various systems of records (SORs)
Creates BI applications that enable analysis of business performance
The DW will store (Facts) in the following subject areas:
Sales
Inventory
Sales Quota
Strategy Plans
The Retail Company had the following products which were sold:
Audio TV and Video Computers Cameras and camcorders Cell phones Music, Movies and Audio Books Games and Toys Home Appliances

The company has 4 sales channels:

Retail
Stores
Catalog
Online
Three top-level geographic regions:

North America
Europe
Asia
Customers who purchased products are tracked in :

Catalog
Online
Retail Company SOR
Database	Business Area	dbms
Retail_SOR_NA	North America	Microsoft SQL Server
Retail_SOR_EU	Europe	MySQL
Retail_SOR_AS	Asia	PostgreSQL
Retail_SOR_CAT	Catalog	Oracle
Flat Files	Cross-unit reference data	csv,text delimited
DW has dimensional model to support:

Sales Analysis
Inventory Analysis
Sales quota & planning analysis
DI: Loading data sources into DW

SOR: flat files, SQL Server, PostgreSQL, MySQL and Oracle
DW: MySQL
ETL: Talend
BI: Dashboards, Reports & Visualizations

Inventory Analysis
Sales quota & planning analysis
Deliverables - Analysis
Data Subjects

Online Sales (FactOnlineSales)
Sales (FactStoreSales)
Inventory (FactInventory)
Sales Quota
Strategy Plan
Types of Analysis:

Trending
Ranking
Comparison
Period over Period
Geo Map
Contribution
Measures:

Sales in $, Profit, Margin, Average order size,...
Dimensions:

Customers: Company & Person, demographics
Product: Product Hierarchy (Category, Subcategory, Product),Brand.
Store: Type, Other attributes
Dates
Geography
