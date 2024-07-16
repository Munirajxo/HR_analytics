# HR Analytics: Insights for Employee Wellness

## Table of Contents 
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Explotary Data Analysis](#explotary-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
## Project Overview
---
This project involved using HR analytics to develop a custom dashboard. I started by constructing a database and writing SQL queries. Then, I created a wireframe, analyzed the data, and built the final dashboard to effectively present the insights

![HR_Analytics_Dashboard](https://github.com/user-attachments/assets/6d42b6dd-62d6-438a-ac38-6bc569cf6ffd)


### Data Sources
---
HR Analytics Data: The dataset used for this analysis is the "Absenteeism_at_work.csv","Reasons.csv","compensation.csv" files, Containing detailed informtion about HR data.
 
### Tools 
---
- SQL Server - Built and connected a database also Developed SQL queries for data extraction.
- Powerbi - Built a interactive dashboard 

### Data Cleaning
---
In the initial preparation phase, We performed following tasks:
1. Build and connected a database.
2. Cleand and organized data using sql queries .
3. Data cleaning and formatting.
   
### Explotary Data Analysis 
---
EDA involved exploring the data to answer questions such as:
- Finding the healthiest employees for bonus?
- Wage increase for the non-smokers?
- Finding the reason for absenteeism?

### Data Analysis 
---
Joined Tables: Combined Absenteeism,Reasons, and Compensation tables using SQL joins.
Aggregate Functions: Calculated average wage increases with functions like AVG.
CASE Functions: Categorized data using CASE statements to identify healthy non-smoking individuals.
Data Filtering: Applied filters to isolate data for healthy non-smokers.
Query Optimization: Enhanced performance by indexing and selecting relevant columns.
Power BI Integration: Connected the optimized SQL query to Power BI to visualize outcomes and insights.

### Results
---
Compensation Increase: The compensation rate increased by $0.68 per hour, amounting to $1,414.40 increase per year for non-smokers, within a budget of $983,221.
Highest Absenteeism: 3 individuals had the highest absenteeism rates.
Weekly Absenteeism: Across all 5 days of the week, the sum of absenteeism time in hours ranged from 553 to 1489.
Percentage Contribution: The 3 individuals accounted for 14.93% of the total absenteeism time in hours.
Monthly and Weekly Analysis: Analyzed absenteeism by month and by day of the week.
Reasons for Absenteeism: Identified reasons for taking leave.


### Recommendations
---
- Focus on high absenteeism individuals with personalized wellness programs.
- Adjust wage increases based on performance and health metrics.
- Investigate and address the causes of high absenteeism on specific days and months.
- Consider flexible scheduling or remote work options to reduce absenteeism.
- Implement flexible work policies to accommodate employee needs.

