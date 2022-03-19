# Credit-default-prediction
Problem statement and Objective:
Credit default means not being able to repay the debt.
An accurate prediction of default can help in balancing risk and return for the bank by charging higher rates and reducing the credit limit for risky customers. Objective of this project is to predict if a customer will default or not, based on his associated attributes.

Given dataset consists of 23 predictor variables with 21 interval variables (Statements, payments, status, age, limit), 2 nominal variables (Marriage, Sex), 1 ordinal variable (Education) and 1 binary target variable (Default). It consists of 10,000 observations.

Step-1: Categorical variables are converted to type str.

Step-2: Checked for missing values but there are no missing values in the given dataset.

Step-3: Dummy variables are created for categorical variables.

Step-4: Checked for correlation among predictors and new features are added.

Step-5: Data is divided into train (70%) and validation (30%) sets. Stratified sampling is performed as the data is imbalanced with less defaulted observations.

Step-6: 2 probability based algorithms (Logistic Regression, Naive Bayes), 2 distance based algorithms (Support Vector Classifier, K-Nearest Neighbors), 2 tree based algorithms (Random Forest, Gradient Boosting) are fitted based on ROC-AUC score calculated with 5-fold cross validation on train dataset. Interval variables are normalized before fitting distance based algorithms. All algorithms are applied with default parameters.

Step-7: Since Gradient Boosting is performing best, based on ROC-AUC score, parameter values are tuned using GridSearch for this model.

Step-8: Model with selected best parameters is re-fitted to train data and used for predictions on validation data.
