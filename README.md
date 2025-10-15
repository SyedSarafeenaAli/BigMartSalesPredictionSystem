# THEORY:-

SUPERVISED LEARNING: Supervised learning is a machine learning technique that uses human-labeled input and output datasets to train artificial intelligence models. The trained model learns the underlying relationships between inputs and outputs, enabling it to predict correct outputs based on new, unlabeled real-world input data.
Labeled data consists of example data points along with the correct outputs or answers. As input data is fed into the machine learning algorithm, it adjusts its weights until the model has been fitted appropriately. Labeled training data explicitly teaches the model to identify the relationships between features and data labels.  

REGRESSION: Regression in machine learning consists of mathematical methods that allow data scientists to predict a continuous outcome (y) based on the value of one or more predictor variables (x). Linear regression is probably the most popular form of regression analysis because of its ease-of-use in predicting and forecasting.

XGBoost Algorithm: The XGBoost algorithm follows a supervised learning method that utilizes gradient boosting to create an ensemble of multiple decision trees. During the training process, the algorithm starts with an initial prediction and computes the residuals based on the predicted values and the observed values. It then creates other decision trees using a similarity score for the residuals, which are then used to generate the output values for each leaf. This process is repeated either until the residuals stop reducing or for a specified number of times. Each subsequent tree learns from the previous ones.

# PROBLEM STATEMENT:-

Retailers like BigMart have historical sales data across multiple stores for many products. They want to be able to predict future sales of each product in each store. The problem is:
Given features about the product (e.g. weight, type, visibility, MRP) and store attributes (e.g. store location, size, age, type), predict the sales (a continuous numeric value) of that product in that store.
Effectively build a regression model that can estimate Item_Outlet_Sales given the other features.
The challenge includes dealing with missing values, categorical encoding, feature engineering, model selection, overfitting, evaluating error metrics.
This is essentially a supervised learning regression problem: predict a continuous target (sales) from mixed-type features (numerical + categorical).

# OBJECTIVES:-

1. DATA PREPROCESSING AND CLEANING:
   
i) Handle missing values (for weight, store size, etc.)

ii) Deal with zeros or invalid values (e.g. zero visibility)

iii) Standardize or unify inconsistent categorical labels (e.g. "LF", "Low Fat", etc.)

2. FEATURE ENGINEERING:
   
i) Create derived features (for example, number of years since establishment for a store)

ii) Transform categorical features to numeric form (one-hot encoding, label encoding)

iii) Possibly interaction terms or aggregation features

3. MODEL BUILDING AND SELECTION:
   
i) Train multiple regression algorithms (e.g. Linear Regression, Decision Tree, Random Forest, XGBoost)

ii) Compare their performance using cross-validation

4. MODEL EVALUATION:
   
i) Use appropriate error metrics (e.g. RMSE, R²) to evaluate model predictions

ii) Compare training vs validation errors to check overfitting

5. PREDICTION AND DEPLOYMENT:
   
i) Use the best performing model to make predictions on test/unseen data

ii) Possibly wrap the model in an application (web app or API) for users to input features and get sales estimates

DATASET AND FEATURES:-

DATASET OVERVIEW:

1) The dataset comprises historical sales data of various products across multiple outlets (stores).
2) It contains product-level attributes, store (outlet) attributes, and the sales target variable.
3) Usually there are two parts: train (with sales) and test (without sales, for which predictions are to be made) datasets.
4) The dataset has mixed types of variables: numeric (continuous) and categorical.
5) There can be missing values (especially in weight, outlet size) and special cases (zero visibility) that require cleaning or imputation.
