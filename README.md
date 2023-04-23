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
![image](https://user-images.githubusercontent.com/28738970/233820497-dce0e7b9-67ce-4481-85e0-4458cf09276d.png)

# My Analysis: #
- In this survey, which included a total of 630 participants, 261 were found to be residing in the United States. As a resident of the US, I am keen to focus my analysis on data pertaining to this region. Notably, the survey reveals that the median age of participants is 29 years old, and the median annual salary is $75,500.
  
  (*Number of Participants in the US, Median Age of Participants, and Median Salary*)
  
  ![image](https://user-images.githubusercontent.com/28738970/233820525-e7df7002-4d25-45c0-8c33-6ab9c1f47ef6.png)

- Median salaries varied across sectors among the participants, with communication services and public sector having the lowest median salary at $53,000, while the others had a median salary of $75,000. However, it is important to note that this finding was based on a smaller sample size of 38 participants working in the communication services and public sector.
- Among the 38 participants working in the public and communication services sector, individuals with a masters degree and those with a high school degree were found to have the highest median salary of $75,000.
- It is worth noting that out of the 38 participants working in the public and communication services sector, 3 held a high school diploma while 17 held a master's degree. This suggests that the median salary figure for individuals with a master's degree may be more reliable due to the larger sample size. 

  (*Drill Through Report of Data Professional in the US by Communication Services and Public Sector*
  
  ![image](https://user-images.githubusercontent.com/28738970/233820809-f1ae6690-4354-4421-af48-9572c5716621.png)

- Among 261 US-based data professionals who participated in the survey, Python was the most popular tool, chosen by 57% of the respondents, followed by R and SQL.
- When it comes to breaking into the field, 39% of the respondents found it to be neither easy nor difficult, while 27% found it to be difficult and 22% found it to be easy.
- In terms of what they value most for their next employment, 46% of the respondents voted for a better salary, while 20% voted for remote work.

  (*Survey responses among 261 US Participants*)
  
  ![image](https://user-images.githubusercontent.com/28738970/233821314-2b391916-531a-40c2-833b-49e27132a9bb.png)

- When asked to rate their job satisfaction on a scale of 1 to 10 based on factors such as management, salary, upward mobility, work/life balance, coworkers, and learning, the survey respondents gave the highest average scores to coworkers and work/life balance. On the other hand, salary received the lowest average satisfaction score, with respondents averaging a score of 5 out of 10.

  (*Satisfaction Score Among 261 US Participants*)
  
  ![image](https://user-images.githubusercontent.com/28738970/233821471-f46df57f-bce7-4638-979a-b3e74346005e.png)

- Out of the 261 participants in the US, 79 were female and 182 were male.
- While the median salary was the same for both genders, the median age of female data professionals was higher at 31 years compared to males at 28 years.
- Based on the survey results related to favorite tools, difficulty breaking into the job, and what they value most for their next job, it seems that the general opinion among the participants is similar between both genders. 
  
  (*Male Participants*)
  ![image](https://user-images.githubusercontent.com/28738970/233821731-ad213324-c537-4536-8930-6e3559df6ac9.png)
  
  (*Female Participants*)
  ![image](https://user-images.githubusercontent.com/28738970/233821739-5fadc201-a9c2-4bcc-9478-67d72287886c.png)

- According to the satisfaction score with their current employment, both male and female participants rated coworkers and work/life balance as the most satisfying aspects of their job. However, on average, female participants gave a lower satisfaction score than male participants. It would be interesting to conduct further analysis to identify the factors that contributed to this disparity in satisfaction between male and female participants.
  
  (*Male Participants*)
  ![image](https://user-images.githubusercontent.com/28738970/233822276-20ec94e7-10a9-4ee8-924b-84db2fe69dfb.png)
  (*Female Participants*)
  ![image](https://user-images.githubusercontent.com/28738970/233822268-21b9f9d7-36d2-4124-a6ec-cc52efa32869.png)
  


#### Disclaimer: #
*The data provided may not fully reflect the real trends due to various factors, such as differences between cultures and trends between countries, the demographics of Alex the Analyst's subscribers, a limited sample size of 630, and the accuracy of the participants' answers. To gain more accurate and precise insights, it may be necessary to gather more data and conduct further research, such as expanding the sample size, including a more diverse group of participants, and conducting surveys across different platforms and regions.*
