# LITA_Class_Project2
Documentation of my class projects while learning Data Analysis with Incubator Hub
## PROJECT: LITA_Capstone_Project
### Project 2
### Outline
[Project Title](#Project-Title)

[Project Overview](#Project-Overview)

[Goals](#Goals)

[Data Sources](#Data-Sources)

[Tools Used](#Tools-Used)

[Data Overview](#Data-Overview)

[Data Cleaning and Preparation](#Data-Cleaning-and-Preparation)

[Exploratory Data Analysis](#Exploratory-Data-Anaysis)

[Data Analysis](#Data-Analysis)

[Findings](#Findings)

[Recommendations](#Recommendations)

[Conclusion](#Conclusion)


#### Project Title: Customer Segmentation for a Subscription Service

#### Project Overview
This Data Analysis project aims to analyze customer data for a subscription service to identify segments and trends. The goal is to understand customer behaviour, track subscription types, and identify key trends in cancellations and renewals.

#### Goals
- Understanding customer behaviours
- Track Subscription Types
- Identify Trends in Cancellations and Renewals
- Make data-driven recommendations to improve customer retention and acquisition

#### Tools Used
- Microsft
    1. Data Cleaning
    2. Data Analysis
    3. Data Visualization
- SQL (Structured Query Language) Server [Download Here](https://www.microsoft.com) for querying of data
- Power Bi Desktop for Visualization[Download Here](https://www.google.com/url?client=internal-element-cse&cx=012684331380167808104:oe5oj--md1a&q=https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads&sa=U&ved=2ahUKEwjQubqQr8GJAxUvUaQEHV7fEFkQFnoECBUQAQ&usg=AOvVaw1759XFBNl5AM71b9k88zga)
- GitHub for Portfolio Building

#### Data Overview
The data set includes the following key attributes
- CustomerID
- Customer Name
- Region
- Subscription Type
- Subscription Start Date
- Subscription End Date
- Active Status: Indicates if the Subscription is currently active or canceled
- Revenue

#### Data Cleaning and Preparation
In the initial phase of the data cleaning and preparations, I performed the following actions;
1. Data Loading and Inspection 
2. Data Assessment where a preliminary review of the data set was conducted to understand the structure, completeness and identify any potential issues as regards the data set.
3. Handling Missing Variables
4. Data Cleaning and Formatting
5. Data Consistency to ensure consistency in data formats across the data set and identify and eliminate duplicate records to enhance data integrity

#### Exploratory Data Analysis
EDA involved the exploring of data to answer some questions about the data such as:
- Subscription Trends
- Average Subscription Duration
- Customer Demographics

#### Data Anaysis
Here is included some basic lines of code or queries or some DAX expressions used during my analysis
##### Analysis done with Excel
Excel formulae were used to calculate metrics such as average subscription duration and number of subscriptions for each subscription type
```EXCEL
average subscription duration		=AVERAGE(Table3[Subscription Duration])
		
number of people with basic		=COUNTIF(Table3[SubscriptionType],D2)
number of people with premium		=COUNTIF(Table3[SubscriptionType],D3)
number of people with standard		=COUNTIF(Table3[SubscriptionType],D5)
```

Data Visualization
- Calculations
  
![EXCEL CUSTOMER DATA CALC](https://github.com/user-attachments/assets/3ef155bd-383e-4673-867d-665c76910abb)

- Pivot Tables

![pivot table 4](https://github.com/user-attachments/assets/feb97caa-9ccb-4036-bd58-89233e700d31)

![Pivot table 5](https://github.com/user-attachments/assets/67e522bf-bbbd-4bfe-853b-01ccaf674282)


- Bar Charts

![Bar chart Customer Data](https://github.com/user-attachments/assets/435a20ca-f044-4b51-b751-ad0e50b455b6)

##### Analysis Done with SQL
Analysis:
- Customer Data was imported to the SQL Server Management Studio
- Analysis was done on the data with the following queries;

1.Retrieve the total number of customers from each region.
 ```SQL
  SELECT REGION, COUNT(*) AS CUSTOMER_PER_REGION FROM [dbo].[CUSTOMER DATA]
  GROUP BY REGION
 ```

2.Find the most popular subscription type by the number of customers.
 ```SQL
SELECT SUBSCRIPTIONTYPE, COUNT (*) AS NUMBER_OF_SUBSCRIPTIONS
FROM [dbo].[CUSTOMER DATA]
GROUP BY SUBSCRIPTIONTYPE
ORDER BY COUNT(SUBSCRIPTIONTYPE) DESC
```
3.Find customers who canceled their subscription within 6 months.
```SQL
SELECT CUSTOMERID
FROM [dbo].[CUSTOMER DATA]
WHERE CANCELED = 1
     AND DATEDIFF(MM,SUBSCRIPTIONSTART,SUBSCRIPTIONEND) <= 6
```
4.Calculate the average subscription duration for all customers.
```SQL
SELECT AVG(SUBSCRIPTION_DURATION) AS AVERAGE_SUBSCRIPTION_DURATION 
FROM [dbo].[CUSTOMER DATA]
OR
SELECT AVG(DATEDIFF(dd,SUBSCRIPTIONSTART,SUBSCRIPTIONEND)) AS AVERAGE_SUBSCRIPTION_DURATION FROM [dbo].[CUSTOMER DATA]
```
5.Find customers with subscriptions longer than 12 months.
```SQL
SELECT CUSTOMERID
FROM [dbo].[CUSTOMER DATA]
```
6.Calculate total revenue by subscription type.
```SQL
SELECT SUBSCRIPTIONTYPE, SUM(REVENUE) AS TOTAL_REVENUE_BY_SUBSCRIPTIONTYPE
FROM [dbo].[CUSTOMER DATA]
```
7.Find the top 3 regions by subscription cancellations.
```SQL
SELECT TOP 3 REGION, COUNT(CANCELED)  AS TOP_3_REGION_BY_SUBSCRIPTION_CANCELLATION 
FROM [dbo].[CUSTOMER DATA]
WHERE CANCELED = 1
GROUP BY REGION
```
8.Find the total number of active and canceled subscriptions.
```SQL
SELECT CANCELED, COUNT(CANCELED) AS TOTAL_NUMBER_OF_ACTIVE_AND_CANCELED_SUBSCRIPTION
FROM [dbo].[CUSTOMER DATA]
GROUP BY CANCELED
```
Data Visualization

![SQL Customer Data](https://github.com/user-attachments/assets/19e10dec-d581-411b-8737-6136490b680e)


##### Power BI Analysis
The aim of using Power BI was to create an interactive dashboard which contains the insights found in EXCEL and SQL. The Dashboard visualizes key customer segments, cancellations, and subscription trends. It also includes slicers for interactive analysis.

Data Visualization

![Power Bi customer data](https://github.com/user-attachments/assets/41f7dd1a-826f-4ec0-aa50-321215e16d2c)


#### Findings
- Key insights:
 1. The most popular Subscription Type is Basic
 2. Total number of active subscriptions is 18.61K
 3. Total number of canceled subscriptions is 15.81K
 4. Average subscription duration is 365.35
  
- Trends and Patterns: There is only minimal differnce in the Revenue generated from the subscription types per region

#### Recommendations
- Enhance customer engagement: Implement Personalized recommendations based on user behavior
- Promote Premium Subscription: Highlight the benefits of Premium Subscription in marketing materials to convert more basic subscribers
- Improve Customer Support: Implement a feedback mechanism for canceled subscriptions to identify specific areas for improvement
 
#### Conclusion
This analysis indicates that while this subscription service has an active base of active customers, there are still a number of canceled subscriptions hence it shows that there is need for improvement in customer engagement and retention startegies. By implementing the recommendations provided, customer satisfaction can be enhanced leading to increased revenue.






