# HR-EMPLOYEE-ANALYSIS-WITH-POWER-BI.

## Table of Content
- [Project Objective](#project-objective)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Dashboard](#dashboard)
- [Result and Findings](#result-and-findings)
- [Recommendation](#recommendation)
- [Limitation](#limitation)
- [Reference](#reference)
  

### Project Objective

Analyze the healthiness of the company generally and provide your recommendation on the way forward.

### Data Source

Provided by the Company in CSV file format to create the following insights Total Employee, Total Male, Total Female, Percentage of Male, Percentage of Female, Total Department, Percentage Retail, Percentage Lay-off, Employee by Year of Service, Employee by Distance Status, Department based on Employment Status, and Employee by Job Satisfaction Rating.

### Tools Used

Microsoft Power BI was used for cleaning, transformation, Analysis, and reporting.

### Data Cleaning and Preparation

I started by loading the Dataset into the Power query editor. I had to study the Dataset to know the Column(s) that need cleaning and/or transformation.

The Dataset has to do with the HR Employee in a particular company. It’s holistic with 41 Columns and over One Million Rows. Some of its Columns are Age, Attrition, Business_Travel, Daily_Rate, Department, Distance_From_Home, Job_Level, Gender, Employee_Number, Hourly_Rate, etc.

I switched my Column views profile to “Column Profiling Based on Entire Data set” from the bottom left of the power query editor to enable access to the entire Columns.

I transformed the Column “Year_At_Company” containing only numbers to “Service_Year” to include the word ‘Years’ after the number in the Column. To execute that I simply went to “Add Column” on the menu bar and did “From Selection” from the “Column From Examples” drop-down arrow.

This action created an extra Column where I wrote “6 Years” because the first row started with 6 as a number. Then after that, I changed the Column header title by double-clicking it.

![Screenshot_142](https://github.com/Solution92/HR-EMPLOYEE-ANALYSIS-WITH-POWER-BI./assets/144762124/6196a126-8b4b-4db8-8f65-efb67cacd22e)
Column name change

The second transformation was on the “Job_Satisfaction_Rating’’ Column. I did a conditional query using the “If” functions in the “Add Conditional Column” windows. I used the following Conditional arguments — 5-Very High, 4-High, 3-Medium, 2-Low, and 1-Very Low.

![Screenshot_143](https://github.com/Solution92/HR-EMPLOYEE-ANALYSIS-WITH-POWER-BI./assets/144762124/49fb430b-ee62-4f51-ac62-70034bbffea3)
Adding Conditional Column

This was done for a detailed understanding of the insights into the Analysis.

![Screenshot_144](https://github.com/Solution92/HR-EMPLOYEE-ANALYSIS-WITH-POWER-BI./assets/144762124/cce07103-b577-40e2-94da-2e88d77f79f9)

No further cleaning nor transformation was done so I loaded my Dataset to Power BI Desktop for further insights and Dashboard creation by clicking on “File” then “Close & Apply”.

On Power BI Desktop, I started by Writing and designing the Title because I just wanted my Canvas settings to be 16.9 which is the normal setting with a white background so I didn’t change that.

### Exploratory Data Analysis (EDA)

Creating Measures: I created all my measures in a table called DAX — Data Analysis Expression.

This is the point of calculation, using different functions to determine or answer questions and/or draw the given insights.

I did this from my “Enter Data” panel in the “Home” menu. On the “Data” pane I made the DAX table active and created the following measures:

- Total Employee
- Total Male
- Total Female
- Total Department
- % Male
- % Female
- Retain
- % Retain
- Lay-off
- % Lay-off
- Employee by Year of Service
- Employee by Distance Status
- Department based on Employment Status
- Employee by Job Satisfaction Rating
- Employee by Employment Status
  
### Data Analysis

Now, here are my measures:

Total Employee: Under my Table tools I selected “New measure” and here is my formula to determine the total number of Employees.
~~~
- Total Employee = COUNTROWS(‘HR Analytics Data’) = 1,000

- Total Male = CALCULATE({Total Employee},’HR Analytics Data’ {Gender} =”Male”) = 584

- Total Female = CALCULATE({Total Employee},’HR Analytics Data’ {Gender} =”Female”) = 416

- Total Department = DISTINCTCOUNTNOBLANK (‘HR Analytics Data’)’ {Department}) = 3

- % Male = DIVIDE ({Male},{Total Employee}, 0) * 100 = 58.40

- % Female = DIVIDE ({Female},{Total Employee}, 0) * 100 = 41.60

NOTE: For me to get the percentage Lay-off and Retain I must calculate the Total Lay-off and Total Retain respectively.

- Retain = CALCULATE (COUNTROWS ‘HR Analytics Data’, ‘HR Analytics Data’), {Employment Status} = “Retain”)

- % Retain = DIVIDE({Retain}, {Total Employee}) * 100 = 91.20

- Lay-off = CALCULATE (COUNTROWS ‘HR Analytics Data’, ‘HR Analytics Data’), {Employment Status} = “Lay-off”)

- % Lay-off = DIVIDE({Lay-off}, {Total Employee}) * 100 = 8.80
~~~

That was all about Measures.

### Dashboard

![Screenshot_145](https://github.com/Solution92/HR-EMPLOYEE-ANALYSIS-WITH-POWER-BI./assets/144762124/1c6a58f2-9550-4150-b51d-815fbb12ff22)

### Result and Findings

Below are the results and my findings from the analyzed table:

 - In the Total Employee by Employment Status visual, the Total Employees for Retain (912) was higher than Lay-off (88).  Retain accounted for 91.20% of Total Employees. 
 - Under Total Employee by Distance Status, At 651, employees living “Very close” had the highest Total Employee and was 317.31% higher than employees living “Very far”, which had the lowest Total Employee at 156.  “Very close” had the highest Total Employee at 651, followed by “Close” at 193 and “Very far” at 156.  “Very close” accounted for 65.10% of Total Employees.  Meanwhile, “Very Close” had 651 Total Employees, “Very Far” had 156, and “Close” had 193.  
 - Meanwhile, in the Total Employee by Service Year Analysis, Total Employee was highest for 5 years at 124, followed by 1 year and 3 years.  5 years accounted for 12.40% of Total Employees.  Across all 35 Service Years, Total Employees ranged from 1 to 124.   
 - In the Total Employee by Job Satisfaction Rating however, we can see that at 327, “High” had the highest Total Employee and was 77.72% higher than “Low”, which had the lowest Total Employee at 184.  “High” had the highest Total Employees at 327, followed by “Medium”, “Very Low”, and “Low”.  “High” accounted for 32.70% of Total Employees.  Across all 4 Job satisfaction Ratings, Total Employees ranged from 184 to 327. 
 - Finally, In the Department Based on Employment Status, at 663, Research & Development had the highest Total Employees and was 1,794.29% higher than Human Resources, which had the lowest Total Employees at 35.  Research & Development had the highest Total Employee at 663, followed by Sales at 302 and Human Resources at 35.  Research & Development accounted for 66.30% of Total Employees.  Sales had 302 Total Employees, Research & Development had 663, and Human Resources 

### Recommendation

- Business Travel: Tailor support or policies based on the needs of employees who frequently travel. Consider offering resources to mitigate potential challenges associated with frequent business trips.
- Job Satisfaction: Conduct surveys or interviews to understand the factors influencing job satisfaction. Implement changes, if necessary, to enhance overall job satisfaction and employee engagement.
- Promotion Status: Review the promotion criteria and ensure transparency in the promotion process. Provide feedback to employees on areas of improvement and career development opportunities.
- Distance Status: Assess the impact of distance on job satisfaction and performance. Consider flexible work arrangements or additional support for employees who face challenges due to distance.
- Training and Development: Invest in training and development programs for employees eligible for promotion. Provide opportunities for skill enhancement and career growth.
- Work-Life Balance: Implement policies or initiatives to support work-life balance, such as flexible work hours or remote work options.
- Performance Metrics: Continuously monitor these metrics to gauge overall workforce engagement. Address any specific areas where performance can be improved.

### Limitation

-	The dataset lacks contextual information, making it challenging to understand the specific factors driving employee attrition, satisfaction, or performance.
-	With a limited set of features, crucial aspects such as performance reviews, project involvement, or leadership assessments are not included, limiting the depth of the analysis.
-	Being a snapshot in time, the dataset may not capture the dynamic nature of employee dynamics and organizational changes over time.
-	The relatively small sample size could hinder the generalizability of findings to a broader population, raising concerns about statistical significance.
-	Categorical data encoding for variables like 'Gender' and 'Business Travel' may introduce biases or limitations in the analysis, affecting the accuracy of insights drawn from the dataset.

### Reference

Several related datasets can be found on the public site









