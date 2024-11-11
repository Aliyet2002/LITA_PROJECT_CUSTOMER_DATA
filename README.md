# LITA_PROJECT_CUSTOMER_DATA

## TABLE OF CONTENT

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning And Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualisation](#data-visualisation)

[Summary](#summary)

[Recommendation](#recommendation)

## Project Overview

This project is aimed at analyzing customer data for a subscription service to identify segments and trends. It is used to understand customer behavior, track subscription types,
and identify key trends in cancellations and renewals.

## Problem Statement

Identifying customer segments to target different marketing strategies effectively

## Data Sources

The type of customer data used is a customer purchase data. It includes:

Customer ID, Subscription Type, demographics, canceled

## Tools Used

 - Microsoft Excel

    i. For Data cleaning

    ii. For Data Analysis

 - SQL - Structured Query Language

- Power Bi for data visualization

- GitHub for portfolio building

## Data Cleaning and Preparation

In the initial phase of the Data Cleaning and prepartions, we perform the following action;

i. Data loading and Inspection

ii. Removing of duplicates

iii. Data cleaning and formating

## Exploratory Data Analysis

EDA Involves the exploring of Data to answer some questions about the Data suche as;

- What is the total number of customers from each region
- Which subscription type is the most popular by the number of customers
- Which subscription type has the highest revenue

## Data Analysis
 
![image](https://github.com/user-attachments/assets/dfe0f6cd-d31e-4c5b-a43e-a78f2f7d1d0d)

```SQL
SELECT region, COUNT(customerID) AS total_customers
FROM [dbo].[LITA CUSTOMERDATA]
GROUP BY region;
```
```SQL
SELECT TOP 1 SubscriptionType,
COUNT(customerID) AS customer_count
FROM [dbo].[LITA CUSTOMERDATA]
GROUP BY SubscriptionType
ORDER BY customer_count DESC;
```
```SQL
SELECT SubscriptionType, SUM(Revenue) AS total_revenue
FROM [dbo].[LITA CUSTOMERDATA]
GROUP BY SubscriptionType;
```
```
SELECT TOP 3 region, COUNT(*) AS cancellation_count
FROM [dbo].[LITA CUSTOMERDATA]
WHERE canceled = 1
GROUP BY region
ORDER BY cancellation_count DESC;
```
```SQL
SELECT canceled, COUNT(*) AS total_count
FROM [dbo].[LITA CUSTOMERDATA]
GROUP BY canceled;
```

## Data Visualisation

![image](https://github.com/user-attachments/assets/506918e6-34d9-40b4-8f8b-4b2ba322b413)

## Summary

The rate of cancellation in Premium And Standard is higher than active.
