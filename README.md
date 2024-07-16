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
```
--Create a join table
use work
select * From Absenteeism_at_work a
left join compensation b
on a. ID = b. ID 
left join Reasons r on
a. Reason_for_absence = r.Number ;

--- find the healthiest Employees for the bonus 
select * From Absenteeism_at_work
where Social_drinker = 0 and Social_smoker = 0 
and Body_mass_index <25 and
Absenteeism_time_in_hours < (select AVG (Absenteeism_time_in_hours) from Absenteeism_at_work)

--- compansation rate increase for non-smoker / budget $ 983,221 do .68 increase per hour / $1414.4 increase per year 
select count(*) as nonsmookers from Absenteeism_at_work
where Social_smoker = 0;

--Optimize this query 
select 
a . ID,
r. Reason,
Month_of_absence,
Body_mass_index,
CASE WHEN Body_mass_index < 18.5 then 'UnderWeight'
     WHEN Body_mass_index between 18.5 and 25 then 'HealthyWeight'
     WHEN Body_mass_index between 25 and 30 then 'OverWeight'
     WHEN Body_mass_index > 30 then 'Obese'
	 ELSE 'Unknown' end as BMI_Category,
CASE WHEN Month_of_absence IN (12,1,2) then 'Winter'
     WHEN Month_of_absence IN (3,4,5) then 'Spring'
     WHEN Month_of_absence IN (6,7,8) then 'Summer'
     WHEN Month_of_absence IN (9,10,11) then 'Fall'
		  ELSE 'Unkown' END as Season_Names,
		  Seasons,
		  Month_of_absence,
		  Day_of_the_week,
		  Transportation_expense,
		  Education,
		  Son,
		  Social_drinker,
		  Social_smoker,
		  Pet,
		  Disciplinary_failure,
		  Age,
		  Work_load_Average_day,
		  Absenteeism_time_in_hours
From Absenteeism_at_work a
left join compensation b
on a.ID = b.ID 
left join Reasons r on
a. Reason_for_absence = r.Number ;
```
- Joined Tables: Combined Absenteeism,Reasons, and Compensation tables using SQL joins.
- Aggregate Functions: Calculated average wage increases with functions like AVG.
- CASE Functions: Categorized data using CASE statements to identify healthy non-smoking individuals.
- Data Filtering: Applied filters to isolate data for healthy non-smokers.
- Query Optimization: Enhanced performance by indexing and selecting relevant columns.
- Power BI Integration: Connected the optimized SQL query to Power BI to visualize outcomes and insights.
  Including sql queries that i worked



### Results
---
- Compensation Increase: The compensation rate increased by $0.68 per hour, amounting to $1,414.40 increase per year for non-smokers, within a budget of $983,221.
- Highest Absenteeism: 3 individuals had the highest absenteeism rates.
- Weekly Absenteeism: Across all 5 days of the week, the sum of absenteeism time in hours ranged from 553 to 1489.
- Percentage Contribution: The 3 individuals accounted for 14.93% of the total absenteeism time in hours.
- Monthly and Weekly Analysis: Analyzed absenteeism by month and by day of the week.
- Reasons for Absenteeism: Identified reasons for taking leave.


### Recommendations
---
- Focus on high absenteeism individuals with personalized wellness programs.
- Adjust wage increases based on performance and health metrics.
- Investigate and address the causes of high absenteeism on specific days and months.
- Consider flexible scheduling or remote work options to reduce absenteeism.
- Implement flexible work policies to accommodate employee needs.

