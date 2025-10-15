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

# DATASET AND FEATURES:-

DATASET OVERVIEW:

1) The dataset comprises historical sales data of various products across multiple outlets (stores).
2) It contains product-level attributes, store (outlet) attributes, and the sales target variable.
3) Usually there are two parts: train (with sales) and test (without sales, for which predictions are to be made) datasets.
4) The dataset has mixed types of variables: numeric (continuous) and categorical.
5) There can be missing values (especially in weight, outlet size) and special cases (zero visibility) that require cleaning or imputation.

FEATURES DESCRIPTION: 

1) Item_Identifier:

i) A unique code or ID for each product (item).

ii) It helps to distinguish different products, but by itself doesn’t directly tell much unless linked with other product features.

2) Item_Weight:

i) The physical weight of the product (in some unit, e.g. kg or grams).

ii) Heavier or lighter items might sell differently (shipping cost, handling, shelf placement) and sometimes missing values here need to be filled in.

3) Item_Fat_Content:
   
i) Indicates whether the product is “Low Fat,” “Regular,” or similar categories.

ii) It’s especially relevant when the product is food or consumable. Customer preferences (health consciousness, diet) may affect sales.

4) Item_Visibility:

i) How visible the product is in the store, as a fraction or percentage of shelf/display area.

ii) A higher visibility means more chance that customers notice the product, hence possibly higher sales. But in this dataset, some products have zero visibility (which is unrealistic), so those are treated specially (imputed).

5) Item_Type:
   
i) Category or classification of the product (for example: “Dairy,” “Frozen Foods,” “Soft Drinks,” etc.).

ii) Helps group similar products—these groups may have similar sales behavior (e.g. perishable vs non-perishable). 

6) Item_MRP:

i) Maximum Retail Price of the product (the list price).

ii) This influences how much customers might pay; generally, price has negative correlation with demand (higher price → fewer sold) but depends on product type and store. 

7) Outlet_Identifier:

i) Unique ID/code for the store (outlet).

ii) Different outlets may have different locations, size, customer base, etc., so knowing which outlet helps to capture those differences.

8) Outlet_Establishment_Year:
   
i) The year when the store/outlet was opened.

ii) Often transformed into “age of outlet” (current year minus establishment year) to reflect experience, maturity, possibly customer awareness, and stability. Older outlets might have more established customer flow. 

9) Outlet_Size:

i) Physical size or capacity of the outlet (e.g. Small, Medium, Large).

ii) Larger stores may carry more variety, have more shelf space, more visibility, draw more customers. Missing values often exist in this feature and need to be filled. 

10) Outlet_Location_Type:
    
i) Type/category of the city or area in which the outlet is located (for example, Tier-1 urban, Tier-2, or rural).

ii) Location affects footfall, purchasing power of customers, competition, etc. A store in a densely populated/urban area may have higher sales compared to one in less dense area. 

11) Outlet_Type:
    
i) What kind of outlet/store it is (for example, Supermarket type, Grocery Store, etc.).

ii) Different business models, product assortments, store layout, pricing strategies etc. influence sales. 

12) Item_Outlet_Sales (Target Variable):
    
i) The actual sales (amount sold) of a particular item in a particular outlet.

ii) This is what the model aims to predict. In the training data it’s known; in the test data, the model must estimate it.
