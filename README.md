# Video_Games_Sales_Prediction
# SC1015 Mini-Project: Video Games Sales and Rating Analysis

This is a Mini-Project for SC1015  (Introduction to Data Science and Artificial Intelligence) which focuses on Video Games Sales and Rating from Kaggle. For detailed walkthrough, please view the source code in order from:

## Table of Contents
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Preparation](#data-preparation)
- [Models Used](#models-used)
- [Outcomes & Insights](#outcomes--insights)
- [Contributors](#contributors)
- [References](#references)

## Problem Definition
 - To predict global sales from various game-related variable such as domestic sales, rating,      genre, platform, user & critic scores to gain insight into consumer preference and market
 - To find out the best model in predicting global sales from numeric & categorical variables

## Data Cleaning
- Removal of null values using `.dropna()`.
- Identification and removal of outliers using the interquartile range formula.
- Conversion of `User_Score` from object data type to numeric data type using `.astype(object).astype(float)`.
- Target encoding for categorical variables like Platform, Genre, Publisher, Developer, Rating using the mean `Global_Sales` for each category as the target value.

## Exploratory Data Analysis
- Univariate analysis for numeric and categorical variables using box plots and histograms.
- Multivariate analysis across all columns using a correlation matrix and pair plots.

## Data Preparation
- Data is split into training and testing sets based on the year. Data from 1985 to 2009 is used for training, and data from 2010 to 2016 is used for testing.

## Models Used
### Linear Regression
- Linear regression is applied to both numeric and categorical variables.

### Lasso Regression
- Lasso regression helps in feature selection and prevents overfitting through a regularization penalty on coefficients.

### Radial Basis Function Network (RBFN)
- RBFN uses radial basis functions for activation and is suited for approximation and time series prediction tasks.

## Outcomes & Insights
- **Numeric Columns:** Lasso regression performs better than Linear regression, with RBFN showing slightly better performance than Lasso.
- **Categorical Columns:** Lasso significantly outperforms Linear regression, though it shows reduced performance in RBFN.
- **Best Regression Model for Prediction:** Lasso Regression.
- **Best Overall Model for Prediction:** Radial Basis Function Network.
- **Best Columns for Global Sales Prediction:** NA_Sales, EU_Sales, Other_Sales for numeric variables; Genre, Developer, Platform for categorical variables.

## Contributors
- **Kalaiselvan Shanmugapriyan** - Data Cleaning & Preparation, EDA, RBFN
- **Manikandan Yuvana** - Data Cleaning, EDA, Lasso Regression
- **Rajadharshini Nedumaran** - Data Cleaning, EDA, Linear Regression

## References
- [IBM on Lasso Regression](https://www.ibm.com/topics/lasso-regression)
- [IBM on Linear Regression](https://www.ibm.com/topics/linear-regression)
- [Converting Categorical Data in Pandas and Scikit-Learn](https://www.turing.com/kb/convert-categorical-data-in-pandas-and-scikit-learn)
- [LinkedIn Article on Game Buying Choices](https://www.linkedin.com/pulse/what-influences-your-choices-when-buying-new-game-teta-studioco/)
- [YouTube Video on Data Science](https://youtu.be/LmpBt0tenJE?feature=shared)
