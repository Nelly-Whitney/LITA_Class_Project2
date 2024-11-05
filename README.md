# LITA_Class_Project2
Documentation of my class projects while learning Data Analysis with Incubator Hub
## PROJECTS: LITA_Capstone_Project
### Project 2
### Outline





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




