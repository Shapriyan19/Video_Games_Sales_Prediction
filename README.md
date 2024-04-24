# Video_Games_Sales_Prediction
# SC1015 Mini-Project: Video Games Sales and Rating Analysis

## About
This is a Mini-Project for SC1015  (Introduction to Data Science and Artificial Intelligence) which focuses on Video Games Sales and Rating from Kaggle. For detailed walkthrough, please view the source code in order from:

- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Preparation](#data-preparation)
- [Linear Regression](#Linear-Regression)
- [Lasso Regression](#Lasso-Regression)
- [Radial Basis Function Network](#Radial-Basis-Function-Network)

## Problem Definition
 - To predict global sales from various game-related variable such as domestic sales, rating,      genre, platform, user & critic scores to gain insight into consumer preference and market
 - To find out the best model in predicting global sales from numeric & categorical variables

## Models Used
- Linear Regression
- Lasso Regression
- Radial Basis Function Network

## Techniques deployed
- Data Cleaning: Removing null values using .dropna(). Finding outliers and removing them using the interquartile range formula. Converting User_Score from object data type to numeric data type with .astype(object) .astype(float)
- Data Cleaning: Target encoding for categorical variables Platform, Genre, Publisher, Developer, Rating. Using mean Global_Sales for each category as the mean target value
- Exploratory Data Analysis: Univariate analysis for numeric and categorical variables using boxplots and histograms
- Exploratory Data Analysis: Multivariate analysis for all columns using correlation matrix and pairplots
- Data Preparation: Splitting  the train and test data according to year with data from 1985 to 2009 is used for training and data from 2010 to 2016 is used for testing. Training on earlier data and testing on later data allows the model to capture and adapt to long-term trends, seasonal variations, and shifts in patterns over time, and models can be used for time-series forecasting.

## Linear Regression
Performed linear regression individually on numeric and categorical columns. Given the linear equation: y = β _x where x is the independent variable and y the dependent variable, the goal of linear regression is to estimate the coefficients (β) that minimise the difference between the observed and predicted values of the dependent variable.

## Lasso Regression
Lasso Regression, a linear method, aids feature selection and prevents overfitting via a regularisation penalty on coefficients. Penalising coefficients' absolute size encourages some to become zero, facilitating feature selection. The objective minimises the Residual Sum of Squares (RSS) and penalty term, while shrinkage constrains the sum of absolute coefficients, reducing model complexity. Choice of regularisation parameter (λ or α) influences feature selection and model complexity, typically determined via cross-validation. Lasso offers simplified, interpretable models and overfitting prevention, particularly in high-dimensional data. Challenges include increased bias and parameter selection for balancing underfitting and overfitting risks. Overall, Lasso Regression simplifies models, vital for interpretable and accurate predictions.

## Radial Basis Function Network
The Radial Basis Function Network (RBFN) is a neural network variant leveraging radial basis functions for activation, primarily suited for function approximation and time series prediction tasks. It consists of an input layer, a hidden layer employing RBF activation, and a linear output layer. The initialization of RBF centres, often accomplished through K-means clustering, is crucial for network performance. During training, RBF outputs are fed into a linear model, typically Ridge Regression, with hyperparameters like the number of centres and the spread of Gaussian functions optimised via cross-validation. RBFNs offer a unique advantage in capturing local data intricacies, although careful consideration of centre placement and the gamma parameter is essential. Despite challenges, RBFNs provide a robust framework for modelling complex, nonlinear relationships, striking a balance between performance and interpretability.

## Outcomes & Insights
- Analysis from Models: For Numeric Columns, Lasso regression performs better than Linear regression. Radial Basis Function performs slightly better than Lasso
- Analysis from Models: For Categorical Columns: Lasso significantly better than Linear, but performance reduces for RBF
- Analysis from Models: Both RBF and Lasso models yield R² values above 0.7, with RBF having slightly lower MSE.
- Outcome: Best Regression model for prediction: Lasso Regression. Lasso regression outperforms linear regression due to its feature selection, reducing overfitting, managing multicollinearity, and enhancing interpretability through L1 regularisation.
- Outcome: Best Model for overall prediction: Radial Basis Function Network. RBFNs perform better than Linear and Lasso function as it is a non-linear model that uses radial basis functions such as Gaussian function to capture complex patterns in data that are not linearly separable
- Outcome: No significant improvement from Lasso to RBFN when predicting categorical columns. While both handle multicollinearity well, RBFN's complex, non-linear modelling may yield only slight improvements over Lasso due to issues like hyperparameter tuning sensitivity, unnecessary complexity for linear relationships, and potential data size.
- Insight: Best Columns for prediction of Global Sales (numeric): NA_Sales , EU_Sales,Other_Sales. Domestic sales are crucial for prediction of global sales as they have a direct impact on global revenue. Furthermore, North America and Europe are the biggest markets for the gaming industry, hence increasing their influence of global sales
- Insight: Best Columns for prediction of Global_Sales (categorical): Genre, Developer, Platform. Genre of the game is a significant factor in determining if the game appeals to users. Similarly, platform & developer is an influential factor in decision-making as it affects the compatibility and accessibility of games with the users, directly affecting sales. 

## Contributors
- **Kalaiselvan Shanmugapriyan** - Data Cleaning & Preparation, EDA, RBFN
- **Manikandan Yuvana** - Data Cleaning, EDA, Lasso Regression
- **Rajadharshini Nedumaran** - Data Cleaning, EDA, Linear Regression

## References
- [IBM on Lasso Regression](https://www.ibm.com/topics/lasso-regression)
- [IBM on Linear Regression](https://www.ibm.com/topics/linear-regression)
- [Converting Categorical Data in Pandas and Scikit-Learn](https://www.turing.com/kb/convert-categorical-data-in-pandas-and-scikit-learn)
- [LinkedIn Article on Game Buying Choices](https://www.linkedin.com/pulse/what-influences-your-choices-when-buying-new-game-teta-studioco/)
- [YouTube Video on Lasso Regression](https://youtu.be/LmpBt0tenJE?feature=shared)
- [Article on Radial Basis Function Network](https://www.sciencedirect.com/topics/engineering/radial-basis-function-network#:~:text=Radial%20basis%20function%20networks%20are,layer%20and%20the%20output%20layer.)
- [Code Reference for RBF](https://gamedevacademy.org/using-neural-networks-for-regression-radial-basis-function-networks/)
