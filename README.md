# Project: Understanding and Predicting Employee Turnover

A case study in prescriptive analytics.
### Project Statement

Portobello Tech is an app innovator that has devised an intelligent way of predicting employee turnover within the company. It periodically evaluates employees' work details including the number of projects they worked upon, average monthly working hours, time spent in the company, promotions in the last 5 years, and salary level.

Data from prior evaluations show the employee’s satisfaction at the workplace. The data could be used to identify patterns in work style and their interest to continue to work in the company.

The HR Department owns the data and uses it to predict employee turnover. Employee turnover refers to the total number of workers who leave a company over a certain time period.

As the ML Developer assigned to the HR Department, you have been asked to create ML Programs to:

1. Perform data quality check by checking for missing values if any.
2. Understand what factors contributed most to employee turnover by EDA.
3. Perform clustering of Employees who left based on their satisfaction and evaluation.
4. Handle the left Class Imbalance using SMOTE technique.
5. Perform k-fold cross-validation model training and evaluate performance. 
6. Identify the best model and justify the evaluation metrics used. 
7. Suggest various retention strategies for targeted employees.

Data source: `HR.csv`

| Column Name             | Description                                                   |
|-------------------------|---------------------------------------------------------------|
| satisfaction_level      | satisfaction level at the job of an employee                   |
| last_evaluation         | Rating between 0 to 1, received by an employee at his last evaluation |
| number_project          | Number of projects, an employee involved in                    |
| average_montly_hours    | Average number of hours in a month, spent by an employee at office |
| time_spend_company      | Number of years spent in the company                           |
| Work_accident           | 0 - no accident during employee stay, 1 - accident during employee stay |
| left                    | 0 indicates employee stays in the company, 1 indicates - employee left the company |
| promotion_last_5years   | Number of promotions in his stay                              |
| Department              | Department, an employee belongs to                            |
| salary                  | Salary in USD                                                 |

### We'll be covering:
- **Descriptive Analytics** - What happened?
- **Predictive Analytics** - What might happen?
- **Prescriptive Analytics** - What should we do?


***
### Objective: 
- To understand what factors contributed most to employee turnover.
- To perform clustering of Employees who left based on their satisfaction and evaluation
- To create a model that predicts the likelihood if a certain employee will leave the company or not. 
- To create or improve different retention strategies on targeted employees.

- ## Steps

### 1. Perform a data quality check to identify any missing values.


### 2. Conduct exploratory data analysis (EDA) to determine the main factors contributing to employee turnover.
   1. Generate a heatmap of the correlation matrix for all numerical features/columns in the dataset.
   1. Plot the distribution of the following variables:
      - Employee Satisfaction (using the "satisfaction_level" column)
      - Employee Evaluation (using the "last_evaluation" column)
      - Average Monthly Hours (using the "average_montly_hours" column)
   1. Create a bar plot showing the Employee Project Count for both employees who left and those who stayed in the organization (using the "number_project" column and the "left" column as the hue). Provide insights based on the plot.


### 3. Perform clustering of employees who left based on their satisfaction and evaluation.
   1. Select the columns "satisfaction_level", "last_evaluation", and "left".
   1. Apply KMeans clustering to the employees who left the company, dividing them into 3 clusters.
   1. Based on the satisfaction and evaluation factors, analyze and describe the characteristics of each employee cluster.


### 4. Address the class imbalance in the "left" variable using the SMOTE technique.
   1. Pre-process the data by converting categorical columns to numerical columns:
      - Separate categorical variables from numeric variables.
      - Apply the get_dummies() function to encode the categorical variables.
      - Combine the categorical and numeric variables.
   1. Split the dataset into training and testing sets using a stratified 80:20 ratio with a random state of 123.
   1. Use the SMOTE technique from the imblearn module to upsample the training dataset.


### 5. Perform 5-fold cross-validation for model training and performance evaluation.
   1. Train a Logistic Regression model and apply 5-fold cross-validation. Plot the classification report.
   1. Train a Random Forest Classifier model and apply 5-fold cross-validation. Plot the classification report.
   1. Train a Gradient Boosting Classifier model and apply 5-fold cross-validation. Plot the classification report.


### 6. Determine the best model and justify the evaluation metrics used.
   1. Calculate the ROC/AUC for each model and plot the ROC curves.
   1. Compute the confusion matrix for each model.
   1. Based on the confusion matrix, explain whether Recall or Precision should be prioritized.


### 7. Provide various retention strategies for targeted employees.
   1. Use the best model to predict the probability of employee turnover in the test data.
   1. Categorize employees into four zones based on the probability scores and suggest appropriate retention strategies for each zone:
      - Safe Zone (Green) (Score < 20%)
      - Low Risk Zone (Yellow) (20% < Score < 60%)
      - Medium Risk Zone (Orange) (60% < Score < 90%)
      - High Risk Zone (Red) (Score > 90%).
