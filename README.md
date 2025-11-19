Heart Disease Risk Prediction
A machine learning project to predict heart disease risk using patient health indicators.

Dataset
Source: Heart Disease Data on Kaggle

Target Variable: Heart disease presence (binary classification)

Project Structure
1. Data Profiling & Initial Analysis
Data loading and basic exploration

Row/column counts and data types

Missing value analysis and duplicate detection

Distribution visualization and outlier detection

Correlation analysis (Pearson for numerical, Cramér's V for categorical)

2. Exploratory Data Analysis (EDA)
Pass A: Raw EDA

Distribution plots (histograms, countplots)

Missing value patterns visualization

Class imbalance analysis

Correlation analysis on complete cases

Pass B: Post-Imputation EDA

Missing value imputation (mean/median for numerical, mode for categorical)

Categorical variable encoding

Statistical testing:

Chi-square tests (categorical vs target)

ANOVA/Kruskal-Wallis (numerical vs target)

Effect size metrics (Cohen's d, η²)

3. Feature Engineering & Statistical Testing
3.1 Outlier Handling

IQR/z-score methods for numerical features

Domain-specific outlier treatment:

chol = 600: Winsorize/log-transform (possible true extreme)

oldpeak = -3: Replace with NaN (impossible value)

3.2 Missing Value Imputation

Numerical: Mean/median/regression imputation

Categorical: Mode/"missing" category

3.3 Feature Transformation

Scaling: StandardScaler, MinMaxScaler, RobustScaler

Encoding: One-hot, ordinal, or target encoding

3.4 Feature Creation

Domain-driven combinations (BMI, age groups, ratios)

Polynomial and interaction terms

3.5 Statistical Feature Selection

ANOVA/Kruskal-Wallis for numerical vs target

Chi-square/Cramer's V for categorical vs target

Pearson/Spearman correlation for numerical relationships

3.6 Multicollinearity Check

Variance Inflation Factor (VIF) analysis

PCA for correlated features

3.7 Model-based Feature Importance

Logistic Regression coefficients

Random Forest/Gradient Boosting importance

SHAP values for interpretability

Model Preparation
Train-test split (80/20 or 70/30)

Feature scaling (fit on training data only)

Baseline models:

Logistic Regression

Random Forest

Gradient Boosted Trees (XGBoost/LightGBM)

Evaluation Metrics
Accuracy, Precision, Recall, F1-score

ROC-AUC and ROC curves

Feature importance analysis
