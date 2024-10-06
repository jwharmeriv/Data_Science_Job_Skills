# Capstone 2: Data Scientist Job Skill Analysis
An exploratory data analysis on data science job skills with a model for predicting the most important skills.

## Project Overview
_Data Scientist and Data Analyst jobs require a specialized set of skills. I want to identify the most in demand skills in the Glassdoor job descriptions for a Data Scientist and Data Analyst, so I know which ones  to focus on developing first to be a more highly rated candidate during my job search. Understanding where these jobs are located and in which industries will allow me to more efficiently focus my search in the appropriate state and industry to increase my odds of getting a job as a Data Scientist or Data Analyst._

## Data
Kaggle is an online community of data scientists and machine learning engineers. Kaggle allows users to find datasets they want to use in building AI models, publish datasets, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges. The data for this dataset was collected by RRK-CODER (Kaggle profile name) through a systematic web scraping process using the Selenium framework. Leveraging Selenium allowed for the automated retrieval and analysis of information from over 1,500 live data science job listings on Glassdoor.com. 

The data encompasses essential details about each job listing, facilitating comprehensive analysis and insights into the data science job market. I decided to focus the analysis on the skills, location, industry, and company ratings for each open position to allow me to prioritize which skills to learn first, which industry is hiring the most data scientists/data analysts, and where these positions are located in the Unites States (including remote positions).

[Glassdoor Data Science Job Listings](https://www.kaggle.com/datasets/rrkcoder/glassdoor-data-science-job-listings/data)

## Method
Describe the methods you used, such as Exploratory Data Analysis (EDA), Feature Engineering, Model Building, and Evaluation Metrics.
There are many types of classification algorithms out there in the wild, but I decided to start with 3.

 - **Logistic Regression:**  Logistic Regression is a simple yet effective linear classifier that works well for text classification tasks. It's interpretable, allowing you to determine which skills have the highest weights, 					which can indicate their demand. It is also computationally efficient and provides easily interpretable results that highlight the most significant features/skills.
       
 - **Random Forest Classifier:**  Random Forest is a powerful ensemble method that combines multiple decision trees to improve accuracy and reduce overfitting. It can also give feature importance scores, which can be used         to identify which skills are most relevant across job descriptions. Random Forest models are capable of handling a large amount of data and are less sensitive to overfitting compared to individual decision trees.
  
 - **Stacked Model (LightGBM + XGBoost):**  LightGBM (Light Gradient Boosting Machine) and XGBoost are both ensemble methods based on boosting, which means they create a series of weak learners (typically decision trees)          that focus on improving errors from previous iterations. This makes them effective at handling complex patterns in data. Since LightGBM and XGBoost may learn different aspects of the data, stacking helps create a             balanced final model as well as mitigating the risk of overfitting by reducing the variance.

I chose to work with the Random Forest model (after trying all 3) in the in end because it is a strong middle ground, offering good performance for a wide variety of tasks while being more scalable and efficient than the stacked model. It balances complexity and predictive power, making it a good general-purpose model, especially when computational resources are available.

## Data Cleaning
To get the data into a better state for analysis and predictive modeling, first I needed to filter out any jobs that did not include "Data Scientist" or "Data Analyst" in the job title. Although some jobs with different titles could essentially be data scientists or data analysts based on the job descriptions, I wanted this to be explicit and not leave any additional room for interpretation regarding job title. I was mostly focused on the skills needed, and this filtering still resulted in over 1,100 records of job titles with Data Scientist or Data Analyst which I deemed sufficient for this exercise. 

Next I needed to indentify the locations of the job openings by state with "Remote" also being considered a location. This was accomplished by a user-defined function that stripped away the city and replaced it with the 2 letter abbreviation for the state. Then a new column "State" was created and updated with the 2 letter state abbreviation which also included "Remote".

Now a list of skills needed to be defined, so I could make predictions on which ones to focus on learning first. While this is a subjective selection, I still feel it is a good selection of skills and software to know based on my previous 8 months of researching open positions. I chose what I considered to be the top 20 most common ones I have seen as well as the ones that appeared in this dataset. In fairness, a more exhaustive list could be created by counting all of the skills and software listed in the dataset. I would also consider updating this list on a yearly basis to capture any new skills or emerging technology/software to stay current.

## EDA
[EDA Report](http://localhost:8888/notebooks/Desktop/Data_Science_Job_Skills/Capstone_2_Final.ipynb)

![Job Title Count](https://github.com/jwharmeriv/Data_Science_Job_Skills/blob/main/Capstone%202/Images/Job%20Title%20Count.png)

- There were 1166 job titles containing Data Scientist and 32 containing Data analyst.

![Skill Counts](https://github.com/jwharmeriv/Data_Science_Job_Skills/blob/main/Capstone%202/Images/Skill%20Counts.png)

![Job Count by State](https://github.com/jwharmeriv/Data_Science_Job_Skills/blob/main/Capstone%202/Images/Job%20Counts%20by%20State.png)

- Remote jobs lead the way with 218, but California was close with 195 job openings which makes up ~16% of the job openings for Data Scientist and Data Analyst positions.

![Industry Count](https://github.com/jwharmeriv/Data_Science_Job_Skills/blob/main/Capstone%202/Images/Industry%20Hiring%20Counts.png)

- I.T. Support Services and Health Care are the leading industries hiring for Data Scientists and Data Analysts and made up 22% of the openings out of the 68 unique industrieis hiring. 

## Modeling
Summarize your findings, highlighting the key insights from the analysis. Use bullet points for clarity.

After testing and tuning all 3 models (Logistic Regression, Random Forest, Stacked LightGBM + XGBoost), I chose the Random Forest model for its scalability, predictive power, and efficiency (especially compared to the stacked model).



## Conclusion
Discuss the implications of your analysis and any recommendations or future work.

## Files
- `Capstone_2_Final.ipynb`: Main Jupyter Notebook with the final analysis and model.
- `data/`: The dataset(s) used in the project.
- `README.md`: This file containing the final project report.

