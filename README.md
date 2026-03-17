# Predicting_Workforce_Engagement_Levels
Employee engagement plays a crucial role in organizational success. High engagement levels are associated with greater productivity, lower turnover. This project aims to predict an employee's likelihood of being engaged or disengaged at work using historical attendance records, health indicators, workload, and personal/workplace factors.

## Project Overview:
Employee engagement plays a critical role in organizational success. High engagement leads to improved productivity, reduced absenteeism, and better workplace.
This project focuses on building a machine learning model to predict employee engagement levels using historical data such as attendance, performance, health indicators, and work-related factors.

## Objectives:
Analyze employee data to identify patterns influencing engagement
Predict workforce engagement levels using machine learning models
Classify employees into:
    High Engagement
    Medium Engagement
    Low Engagement
Help organizations take proactive steps to improve employee engagement

## Dataset Description:
The dataset contains various employee-related attributes, including:
Attribute	                       |         Description
employee_id	                     |         Unique identifier assigned to each employee
absence_reason_code	             |         Encoded reason for absence (predefined categories)
absence_month	                   |         Month in which the absence occurred
weekday_code	                   |         Numeric code representing the day of the week
season_indicator	               |         Season of the year (Winter, Spring, Summer, Fall)
commute_cost	                   |         Monthly commuting expense
commute_distance	               |         Distance in kilometers from home to workplace
years_at_company	               |         Number of years the employee has worked in the organization
employee_age	                   |         Age of the employee
daily_workload	                 |         Average daily workload in standardized units
performance_target	             |         Percentage of performance goal achieved
disciplinary_action	             |         Indicates if disciplinary action was taken (1 = Yes, 0 = No)
education_level	                 |         Employee’s education level
dependents	                     |         Number of children or dependents
alcohol_consumption	             |         Indicates alcohol consumption (1 = Yes, 0 = No)
tobacco_use	                     |         Indicates smoking status (1 = Yes, 0 = No)
pet_count	                       |         Number of pets owned
body_weight_kg	                 |         Employee body weight in kilograms
body_height_cm	                 |         Employee height in centimeters
bmi_score	                       |         Body Mass Index calculated from height and weight
absence_duration_hours	         |         Total hours of absenteeism recorded
engagement_level                 |         Target variable derived from absence and performance: High, Medium, Low


## Data Preprocessing:
Removed columns with missing values
Encoded categorical variables using Label Encoding
Created target variable (engagement_level) based on:
    Absence duration
    Performance target
    Disciplinary action
Scaled features using RobustScaler

## Exploratory Data Analysis (EDA):
Correlation heatmap to identify relationships between features.
Distribution plots for absence_duration_hours and other numeric features.
Scatterplots and boxplots to visualize relationships between absenteeism, age, commute distance, and months.

## Model Implementation:
    1. Logistic Regression:
        Linear classifier for multi-class engagement prediction.
        Weighted classes using class_weight="balanced" to handle imbalance.

    2. Random Forest Classifier:
        Ensemble tree-based model to improve prediction over single trees.
        Class weights balanced using class_weight="balanced".
        Hyperparameter tuning performed (e.g., max_depth, n_estimators, min_samples_split) to optimize accuracy.

    3. XGBoost Classifier:
        Gradient boosting model ideal for tabular data.
        Hyperparameter tuning performed using RandomizedSearchCV for parameters like:
        n_estimators, max_depth, learning_rate, subsample, colsample_bytree, min_child_weight, gamma.
        Feature importance visualized to identify top drivers of engagement.

## Evaluation Metrics:
    Accuracy: Overall correctness of predictions.
    Precision, Recall, F1-score: Class-wise performance metrics.
    Confusion Matrix: To visualize misclassifications.

## Results:
    Logistic Regression: Moderate performance due to linear nature.
    Random Forest: Good handling of non-linear relationships, accuracy ~78%.
    XGBoost: Best performance, accuracy ~82% with hyperparameter tuning.

## Conclusion:
    XGBoost with tuned hyperparameters gave the best prediction results.
    Absenteeism, performance targets, and disciplinary actions are strong indicators of engagement levels.
    This predictive model can help management identify disengaged employees and take proactive measures to improve overall workforce engagement.

