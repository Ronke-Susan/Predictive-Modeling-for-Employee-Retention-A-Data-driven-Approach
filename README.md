# Predictive-Modeling-for-Employee-Retention-A-Data-driven-Approach

**Project Objective**: To predict whether an employee will leave or stay

**Dataset Information**:

*Source* : [Kaggle]('https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction/')

*Shape*: The dataset contains 14,999 rows of data and 10 columns

*Data Dictionary*: 

satisfaction_level:	Employee-reported job satisfaction level [0–1]

last_evaluation:	Score of employee's last performance review [0–1]

number_project:	Number of projects employee contributes to

average_monthly_hours:	Average number of hours employee worked per month

time_spend_company:	How long the employee has been with the company (years)

Work_accident:	Whether or not the employee experienced an accident while at work

left:	Whether or not the employee left the company

promotion_last_5years:	Whether or not the employee was promoted in the last 5 years

Department:	The employee's department

salary:	The employee's salary (U.S. dollars)

**Data Preprocessing**

Gathered basic information and descriptive statistics of the data using df.info() and df.describe() functions respectively

The data was explored to find out if there were any anomalies. The following process where performed on the data.
1. Data Cleaning: Inconsistencies in column names were addressed by renaming columns using .rename() method e.g renamed 'time_spend_company' column as'tenure'. Also missing data was checked for but none were found
2. Outliers: There were outliers in dataset that were later removed during logistic regression model building

**Exploratory Data Analysis**

Variables in the dataset were compared with each other to observe their relationships using boxplots, histograms and heatmap.

The following insights were gathered during exploration:

1. Approximately 17% of Salifort Motors employee left the company
2. Employees who were assigned 7 projects left the company
3. The maximum number of projects assigned to employees seems to be 3-4. The ratio of employees within this project group that left to the ones that stayed is very small
4. Categories of employees who left include:
* Dissatisfied employees with shorter tenures and very satisfied employees with medium length-tenures.
5. The longest-tenured employees didn't leave. Their satisfaction levels aligned with those of newer employees who stayed.
6. Four-year employees who left seem to have an unusually low satisfaction level
7. Mean and median satisfaction scores of employees who left are lower than those who stayed.

**Model Building and Evaluation**
The models used to predict the target variable 'left' were logistic regression model and Decision Trees Model

The evaluation metrics used for both models are accuracy score, precision, f1 score, recall. A confusion matrix was plotted to see how both models performed in predicting true positives, true negatives, false positives and false negatives. The AUC score was used to evaluate the decision tree model

Cross validation was performed on decision tree model using GridSearchCV to find the best parameters that were later used to tune the model.

Logistic regression model assumptions were confirmed before using the model. These are:
* the outcome variable is categorical
* observations are independent of each other
* there was no severe multicollinearity among X variables
* No extreme outlier (outliers were removed)
  
The best performing model was chosen based on the AUC score. The Decision Tree Model
