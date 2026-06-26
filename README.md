Heart Disease Risk Prediction
Project Overview

This project develops an end-to-end machine learning pipeline for predicting the presence of heart disease using patient clinical measurements. The objective is to build a reliable classification model while following a structured data science workflow that emphasizes data quality assessment, statistical analysis, feature engineering, model evaluation, and interpretability.

Dataset: Heart Disease Dataset (Kaggle)

Problem Type: Multi-class Classification

Data Quality Assessment

Before training any model, the dataset was thoroughly examined for data quality issues.

Duplicate Analysis
No duplicate records were found in the dataset.
Missing Value Analysis

The dataset contained significant missing values, especially in the following features:

Feature	Missing Values
ca	611
thal	486
slope	309
fbs	90
oldpeak	62
trestbps	59
thalch	55
exang	55
chol	30
restecg	2

A missing-value heatmap was generated to visualize missingness patterns. The feature ca contained the largest proportion of missing values, followed by thal and slope.

Exploratory Data Analysis

Exploratory analysis was performed to understand the characteristics of the dataset before preprocessing.

Outlier Detection

Boxplots were used to identify potential outliers.

Key observations included:

trestbps: invalid value of 0 and unusually high blood pressure values.
chol: invalid value of 0 and several extremely high cholesterol values (>400).
thalch: unusually low heart rate values.
oldpeak: impossible negative values (<0).

These observations guided subsequent preprocessing decisions.

Class Distribution

The distribution of heart disease severity classes was analyzed to understand class imbalance.

Additional exploratory analysis included:

Target class distribution
Gender distribution
Numerical feature distributions
Correlation analysis between clinical variables
Data Preprocessing

The preprocessing pipeline was implemented using Scikit-Learn's Pipeline and ColumnTransformer.

Outlier Treatment
Replaced invalid blood pressure values (trestbps = 0) with missing values.
Clipped impossible oldpeak values to a valid clinical range.
Missing Value Imputation

Numerical features:

Mean imputation

Categorical features:

Most frequent category imputation
Feature Transformation

Numerical features:

StandardScaler

Categorical features:

One-Hot Encoding (drop='first')

The entire preprocessing workflow was encapsulated in reusable pipelines to prevent data leakage.

Machine Learning Models

The following classification models were trained and compared:

Logistic Regression
Decision Tree
Random Forest
XGBoost
Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|---------:|----------:|-------:|---------:|
| XGBoost | **0.6196** | **0.5884** | **0.6196** | **0.5979** |
| Random Forest | 0.5924 | 0.5531 | 0.5924 | 0.5684 |
| Decision Tree | 0.5598 | 0.4882 | 0.5598 | 0.5123 |
| Logistic Regression | 0.5489 | 0.4841 | 0.5489 | 0.5059 |
 
After changing the problem to binary classification results changed to: 
| Model | Accuracy | Precision | Recall | F1-Score |
|-------|---------:|----------:|-------:|---------:|
| Logistic Regression | 0.8043 | 0.8476 | 0.8165 | 0.8318 |
| Decision Tree | 0.8370 | 0.8559 | 0.8716 | 0.8636 |
| Random Forest | **0.8696** | **0.9048** | 0.8716 | 0.8879 |
| XGBoost | **0.8696** | 0.8972 | **0.8807** | **0.8889** |

Among all evaluated models, XGBoost achieved the best overall performance.

Additional Analysis

The project also includes:

Feature importance analysis
Correlation analysis
Missing value visualization
Outlier visualization
Feature preprocessing pipelines
Model comparison using multiple evaluation metrics
Technologies Used
Python
NumPy
Pandas
Matplotlib
Scikit-Learn
XGBoost
Key Learnings

This project demonstrates an end-to-end data science workflow, including:

Data quality assessment
Missing value analysis
Outlier handling
Exploratory Data Analysis (EDA)
Feature preprocessing using Scikit-Learn Pipelines
Machine learning model comparison
Performance evaluation using Accuracy, Precision, Recall, and F1-score
Building reproducible preprocessing and training pipelines
