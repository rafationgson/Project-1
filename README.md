# Exploratory Data Analysis and Machine Learning project of the Data Analyst jobs in the US.

The dataset is from Kaggle, and it was scraped from the Glassdoor website: https://www.kaggle.com/andrewmvd/data-analyst-jobs

The purpose of this project is to find the factors that correlate with the salary of data analyst jobs. After the data exploration, I intend to make a machine learning model to predict the salary of a data analyst job based on this dataset. This can be used for people applying to Data Analyst jobs, so that they have an idea of what salary they should expect. I would like to cite the Github project of Ken Jee as this helped give me insight in conducting this project: https://github.com/PlayingNumbers/ds_salary_proj. 

## Project at a glance:

Code used: Python
Libraries used: Numpy, Matplotlib, Pandas, Seaborn, Scikit Learn

### Data Cleaning
1. Extracted the salary from the given salary range, in order to get the min, max and average.
2. Classified the data analyst jobs into different classes such as Data Analyst, Business Data Analyst, Financial Data Analyst, Marketing Data Analyst, Healthcare Data Analyst, and Data Quality Analyst.
3. Added a column classifying if they were a senior, junior, or associate
4. Extracted the job state and city.
5. Added a column stating the number of competitors
6. Added columns stating if the job included skills such as Python, R, Excel, Tableau, and SAS.

### Data Exploration
The list below consists of some of the most relevant insights from the dataset
1. The State of California was paying the highest average salary for data analysts.
2. Jobs that required Python or Tableau skills had a significantly higher average salary.
3. The Biotech & Pharmaceuticals Sector, and the Drug & Health Stores industry paid the highest for Data Analysts.

### Model Building
I split the data into 80% for training the model and 20% for testing the model, and the models I used are regression models.
Models used:
1. Linear Regression
2. Random Forest Regression
3. Support Vector Machines

The measure used to evaluate the models was the Mean Absolute Error.
Results of the cross validation scores:
1. Linear Regression = -170312869.96464953
2. Random Forest Regression = -14.157836666666666
3. Linear SVR = -31.758217518788545
4. SVR (kernel='rbf') = -17.54349943670496

The Random Forest Regression performed the best with the lowest MAE, and so this model was fine tuned using a GridSearchCV.

Test Predictions:
Random Forest Regression = 14.604573170731708

### Findings:
Since the average salary in the dataset has a fairly wide distribution and a standard deviation of 23.605836, the results of the Random Forest Regression also reflect that but it is still within the range and has a decent MAE.
