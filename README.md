# salarypredictionportfolio
Salary Prediction Project (Python)

## Define the Problem
Recruiting candidates for an open job position can be a challenging task. Knowing the latest tools, hiring trends, and and benefits to offer a candidate are key to attracting new talent that suits a company’s needs. A pivotal point in a job offer is the salary. Accurately determining the right salary, can attract the right candidate and also help retention of that employee.

Here, I use machine learning methods to analyze a dataset containing features and the salary advertised in various job descriptions.

## Task

To build a machine learning model that accurately predicts the salary of a new job posting based on a set of one million previous job postings.

### Deliverables
- a file that contains the salary predictions
    - data/test_salaries.csv
- the code used to solve the problem
    - EDA
    - Modeling

## Discover
The data was examined in the EDA file.

### Data Collection
The data used for this project was provided.
1. train_features.csv - a unique jobId column and features of the job posting
2. train_salaries.csv - the corresponding salaries for the unique jobId's
3. test_features.csv - a similar dataset as train_features.csv, containing features of a job posting.

Each file was loaded into a pandas dataframe.
The train_features and test_features contained the same features
The train_salaries df contained only jobId and salary information.

### Data Exploration

The training features df contained two numeric and five categorical features. All the jobId values were found to be unique and used to merge the training features and salary df together.

This data was checked for missing values and for outliers.
    - No missing values were found.
    - Using the IQR rule, five values in the salary variable were removed.

For each numerical feature, two plots were made: a distribution plot and a plot that shows the dependency of salary on each feature

Summary of features:
    - Company ID : The salary is not dependent on the company
    - Job Type : With increasing seniority, there is a positive correlation between job type and salary.
    - Degree : Having a higher degree of education positively correlates with an increase in salary
    - Major : Selecting the major of engineering, business, or math are correlated with higher salaries
    - Industry : The oil and finance industries have higher salaries
    - Years of Experience : There is a positive correlation between years of experience and salary
    - Miles from metropolis : In general, salary decreases with increasing distance to a metropolis.

Next, use label encoding to encode each category using salary average to replace the label. Now, using a correlation matrix, we can see the correlation coefficient of each feature with salary as well as with other features.

### Establishing a baseline

Before any advanced modeling, a baseline for determining what features will be established using linear regression. Using cross validation score and MSE as the scoring method, a baseline MSE of 400 was calculated.

As a regression problem, other models that may be suitable to solving this problem are Random Forest and Gradient Boosted Regression.

## Develop Model

Using MSE as an evaluation metric, create and test several models, with a goal of achieving an MSE < 360.

### Engineer Features

Before modeling, the categorical features in the data sets were encoded using the one hot encoding method.

## Create and Test Models

In addition to Linear Regression, a second Linear Regression with data standard and principle component analysis for dimensionality reduction, Random Forest Regressor, and Gradient Boosting Regressor models were tested.

For each model, the MSE was calculated. The model with the lowest MSE was determined to be the Gradient Boosting Regressor.

The predicted values were stored in a .csv file.

The important features constructed by the Gradient Boosting Regressor model were visualized and saved in a .csv file.

