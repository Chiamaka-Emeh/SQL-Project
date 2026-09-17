# Retail Sales SQL Analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Tools Used](#tools-used)
- [Dataset](#dataset)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Cleaning](#data-cleaning)
- [Answers To Business Questions](#answers-to-business-questions)
- [Findings and Business Interpretation](#findings-and-business-interpretation)
- [Recommendations](#recommendations)
- [Project Limitations](#project-limitations)
- [Project Documentation](#project-documentation)

 ## Project Overview
This project involved analysing retail sales data using Microsoft SQL Server. The analysis covered exploratory data analysis, data cleaning and
SQL queries used to examine sales performance, customer purchasing patterns and transaction activities. The project also involved answering a series of business questions
and interpreting the results from the analysis.

## Objectives

The main objectives of the analysis were to:

- Understand the structure and contents of the sales data.
- Check the data for missing values and other data-quality issues.
- Clean the data before carrying out the analysis.
- Examine sales performance across product categories.
- Analyse customer purchasing patterns.
- Identify high-value customers.
- Examine monthly sales patterns.
- Understand transaction activity at different times of the day.

  ## Tools Used
- Microsoft SQL Server

  ## Dataset

The dataset contained 2,000 retail sales records.

The available fields included:

- Transaction ID
- Sale Date
- Sale Time
- Customer ID
- Gender
- Age
- Category
- Quantity
- Price per Unit
- COGS
- Total Sale

The original CSV dataset used for the project is no longer available. The project report and screenshots of the SQL queries and results are
included in this repository to preserve the work carried out during the analysis.

# Exploratory Data Analysis

Exploratory data analysis (EDA) was carried out before answering the
business questions.

The initial analysis focused on understanding the database structure, examining the available columns, checking the number of records and
checking the data for missing values.

### Database and Table Exploration

The database objects and table structure were examined using `INFORMATION_SCHEMA.TABLES` and `INFORMATION_SCHEMA.COLUMNS`.
-- Explore all object in the database  
SELECT * FROM INFORMATION_SCHEMA.TABLES  
-- Explore all columns in the Database  
SELECT * FROM INFORMATION_SCHEMA.COLUMNS  
WHERE TABLE_NAME = 'SQL - Retail Sales Analysis - SQL - Retail Sales Analysis'  

### Record/Rows Count
-- Count rows  
SELECT COUNT(*) AS TotalRows FROM [SQL - Retail Sales Analysis - SQL - Retail Sales Analysis] ;
The query ran successfully and gave TotalRows = 2000 

## Data Cleaning

The columns were checked for missing values before the analysis. The check identified: 10 missing age records, 3 missing quantity records, 3 missing price-per-unit records, 3 missing COGS records, 3 missing total-sale records

The missing age values were handled by creating an age_flag column
to distinguish records where age was known from those where it was
missing. Records with missing quantity, price per unit, COGS or total sale were removed because these fields were needed for the sales analysis.

## Answers To Business Questions
The business questions were answered with SQL queries
i.  Retrieve all columns for sales made on '2022-11-05'  
