# Capstone 2: Data Scientist Job Skill Analysis
An exploratory data analysis on data science job skills with a model for predicting the most important skills.

## Project Overview
_Data Scientist and Data Analyst jobs require a specialized set of skills. I want to identify the most in demand skills in the Glassdoor job descriptions for a Data Scientist and Data Analyst, so I know which ones  to focus on developing first to be a more highly rated candidate during my job search. Understanding where these jobs are located and in which industries will allow me to more efficiently focus my search in the appropriate state and industry to increase my odds of getting a job as a Data Scientist or Data Analyst._

## Data
Kaggle is an online community of data scientists and machine learning engineers. Kaggle allows users to find datasets they want to use in building AI models, publish datasets, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges. The data for this dataset was collected by RRK-CODER (Kaggle profile name) through a systematic web scraping process using the Selenium framework. Leveraging Selenium allowed for the automated retrieval and analysis of information from over 1,500 live data science job listings on Glassdoor.com. 

The data encompasses essential details about each job listing, facilitating comprehensive analysis and insights into the data science job market. I decided to focus the analysis on the skills, location, industry, and company ratings for each open position to allow me to prioritize which skills to learn first, which industry is hiring the most data scientists/data analysts, and where these positions are located in the Unites States (including remote positions).

[Glassdoor Data Science Job Listings](https://www.kaggle.com/datasets/rrkcoder/glassdoor-data-science-job-listings/data)

## Methods
Describe the methods you used, such as Exploratory Data Analysis (EDA), Feature Engineering, Model Building, and Evaluation Metrics.
There are many types of classification algorithms out there in the wild, but I decided to start with 3.

  **1. Logistic Regression:**  Logistic Regression is a simple yet effective linear classifier that works well for text classification tasks. It's interpretable, allowing you to determine which skills 
       have the highest weights, which can indicate their demand. It is also computationally efficient and provides easily interpretable results that highlight the most significant features/skills.
       
  **2. Random Forest Classifier:**  Random Forest is a powerful ensemble method that combines multiple decision trees to improve accuracy and reduce overfitting. It can also give feature importance scores, which can be used         to identify which skills are most relevant across job descriptions. Random Forest models are capable of handling a large amount of data and are less sensitive to overfitting compared to individual decision trees.
  
  **3. Stacked Model (LightGBM + XGBoost):**  LightGBM (Light Gradient Boosting Machine) and XGBoost are both ensemble methods based on boosting, which means they create a series of weak learners (typically decision trees)          that focus on improving errors from previous iterations. This makes them effective at handling complex patterns in data. Since LightGBM and XGBoost may learn different aspects of the data, stacking helps create a             balanced final model as well as mitigating the risk of overfitting by reducing the variance.

## Results
Summarize your findings, highlighting the key insights from the analysis. Use bullet points for clarity.

## Conclusion
Discuss the implications of your analysis and any recommendations or future work.

## Files
- `Capstone_2_Final.ipynb`: Main Jupyter Notebook with the final analysis and model.
- `data/`: The dataset(s) used in the project.
- `README.md`: This file containing the final project report.

