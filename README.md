# Data Professional Survey Analysis
[Survey sourced from YouTube channel, Alex The Analyst.](https://www.youtube.com/watch?v=pixlHHe_lNQ&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=42)

#### NOTE: For this project, I used SQL to clean and transform the dataset and Power BI to visualize the data. I set myself the self-challenge of using SQL instead of Power Query for further customization of the dataset.

# Resources Used for this Project: #
- Stack Overflow and other online forums to research SQL queries.
- Cole Nussbaumer Knaflic's book, *Storytelling with Data*, to reference best practices for data visualization. 
- Alex The Analyst's Youtube channel for the survey dataset. 

# Objectives: #
This study aims to analyze various aspects of the data profession, including market rates based on categorical factors such as industry, education, role, gender, age, race, and country. Additionally, the study will explore the common opinions and satisfaction scores of data professionals in relation to their employer, including factors such as management, salary, upward mobility, work/life balance, coworkers, and learning opportunity. The study will also examine where data professionals place the most value on future employment and the most popular tools used by this profession. Through this analysis, the study aims to provide valuable insights into the current trends and preferences of the data profession.

# Discovery: #
- The dataset is a single flat file in CSV format.
- It contains 28 columns related to questions about the data professionals' profession and background information.
- The dataset has 630 rows representing the data professionals' responses.
- There are some columns that can be dropped for the analysis.
- There are a few missing values that need to be addressed.
- I will clean and structure the dataset using Microsoft SQL Server Management Studio.

# Joining: #
- I used the import wizard in SMSS to load the dataset.
- Since the survey data has various individual inputs, I will need to standardize them by searching for keywords and grouping them based on common attributes.
- The analysis does not require the joining of any new datasets.

# Cleaning, Structuring, and Validating: #
- I dropped columns [Dates Taken], [Time Taken], [Browser], [OS], [City Taken], [Country Taken], [Referrer], and [Time Spent] as they contained minimal data and were not relevant for my analysis.
- To facilitate easier querying in my relational database management system (RDBMS), I renamed the column headers that were too long and inefficient.
- I created a backup of the original dataset before proceeding with further restructuring. 
- In the columns [current_role], [industry], [favorite_tool], [most_important_aspect_for_next_job], [country of origin], and [ethnicity], users were given the option to input "Other" and specify their answers.
- To standardize the values in the [current_role] column, I used wildcards to identify specific keywords such as "Analyst" and "Engineering" and grouped them into general roles like "Data Analyst" or "Data Engineer." This was done to reduce the spread of roles and improve the weight of the analysis.
- The [industry] column contained individual inputs that were grouped into general sectors based on The Global Industry Classification Standard (GICS).
- I grouped user input with SQL in the [favorite_tool] column as a new category. The rest were labeled as "Other" as there was no common attribute. 
- The [most_important_aspect_for_next_job] column contained individual inputs that were not easily categorized, so they were grouped as "Other."
- In the [Country] column, I corrected spelling errors and removed unnecessary white spaces.
- The [Ethnicity] column contained individual inputs that were categorized into standard ethnic groups. For example, "Indian" was moved to the "Asian or Asian American" group.
- Missing values in the [education_level] column were grouped as "Other." 

# Presenting: #
- Validated each column's distinct values to ensure data cleanliness.
- Confirmed that all values were standardized.
- Determined key metrics such as total participant count, median age, and median salary.
- Selected card visualization to showcase these metrics.
- Visualized satisfaction scores using a gauge that ranged from 1 to 10.
- Employed line and bar charts to best illustrate distribution among survey responses
- Used charts to show how median salaries were impacted by education and sectors.
- Created a slicer to allow for drill-through reports based on participants' categorical attributes such as role, gender, age, ethnicity, and country.
- Slicer enabled deeper insights into specific groups within the dataset.

# Dashboard: #
![image](https://user-images.githubusercontent.com/28738970/233547152-4f3a1913-b8f9-40b6-a3e5-11b3035a48ea.png)

#### Disclaimer: #
*The data provided may not fully reflect the real trends due to various factors like differences in salary rates among countries, the demographics of the viewers of Alex the Analyst, a restricted number of participants, and the precision of their answers. To gain more accurate and precise insights, it may be necessary to gather more data.*
