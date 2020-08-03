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