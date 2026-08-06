# food-delivery-time-prediction
Machine learning project for predicting food delivery times

# Food Delivery Time Prediction

A machine learning project for predicting food delivery duration using delivery personnel, location, traffic, weather, vehicle, and order-related features.

## Project Overview

Online food-ordering platforms need to provide customers with reliable delivery-time estimates. Large differences between the estimated and actual delivery times can reduce customer satisfaction, weaken trust in the platform, and create operational difficulties.

The objective of this project is to develop and compare machine learning models that predict food delivery times as accurately as possible. The project also aims to identify the factors that have the greatest influence on delivery duration.

This repository contains the complete machine learning workflow, including:

* Exploratory data analysis
* Data cleaning and preprocessing
* Feature engineering
* Feature selection
* Model training
* Hyperparameter tuning
* Model validation
* Final model evaluation
* Prediction analysis

## Problem Statement

The task is formulated as a supervised regression problem.

Given information about a food delivery order, the model predicts:

```text
Time taken (min)
```

Delivery duration may be influenced by factors such as:

* Restaurant and customer locations
* Delivery distance
* Traffic conditions
* Weather conditions
* Order time
* Delivery personnel characteristics
* Vehicle type
* Order preparation and pickup conditions

The main challenge is that these variables may interact in complex and nonlinear ways.

## Dataset

This project uses the **Food-Delivery** dataset available on Hugging Face:

https://huggingface.co/datasets/aneesarom/Food-Delivery

The dataset contains approximately **45,600 delivery records** and **20 columns**.

The predefined dataset splits contain approximately:

| Dataset Split | Number of Records |
| ------------- | ----------------: |
| Training set  |            36,500 |
| Test set      |             9,120 |
| Total         |            45,600 |

The target variable is:

```text
Time taken (min)
```

The available features include information about:

* Delivery personnel
* Restaurant location
* Customer location
* Vehicle characteristics
* Weather conditions
* Traffic conditions
* Order conditions
* Delivery duration

## Machine Learning Workflow

### 1. Data Exploration

Exploratory data analysis will be used to understand:

* Feature distributions
* Missing values
* Duplicate observations
* Relationships between variables
* Potential outliers
* Target-variable distribution
* Categorical feature balance

### 2. Data Preprocessing

The preprocessing stage may include:

* Cleaning missing and inconsistent values
* Standardizing date and time formats
* Encoding categorical variables
* Scaling numerical variables where necessary
* Validating location-related features
* Identifying potential data-quality issues
* Examining unusual delivery observations

Outliers will be evaluated carefully to distinguish invalid records from valid but uncommon delivery cases.

### 3. Feature Engineering

Potential engineered features include:

* Delivery distance
* Pickup delay
* Order preparation duration
* Time of day
* Day of the week
* Courier age groups
* Courier rating groups
* Traffic and weather interaction features
* Vehicle and distance interaction features

### 4. Data Splitting

The dataset already provides separate training and test sets.

A validation set will be created from the original training data and used for:

* Model selection
* Hyperparameter tuning
* Early stopping
* Performance comparison

The test set will remain untouched until the final evaluation.

To prevent data leakage, preprocessing operations such as imputation, scaling, and categorical encoding will be fitted only on the training data.

## Models

The following regression models are planned for evaluation.

### Baseline Models

* Linear Regression
* Ridge Regression

These models provide interpretable baseline results and help determine whether more complex models produce meaningful improvements.

### Tree-Based Models

* Random Forest Regressor
* LightGBM Regressor
* XGBoost Regressor
* CatBoost Regressor

Tree-based models are expected to perform well because they can capture nonlinear relationships and complex interactions between delivery-related features.

CatBoost may be especially useful for handling categorical variables.

### Neural Network Model

* MLP Regressor

### Ensemble Methods

Stacking or other ensemble approaches may also be tested by combining linear and tree-based models.

## Evaluation Metrics

The models will be evaluated using multiple regression metrics.

### Mean Absolute Error

Mean Absolute Error, or MAE, measures the average absolute difference between predicted and actual delivery times.

Because the result is expressed in minutes, it is easy to interpret.

### Root Mean Squared Error

Root Mean Squared Error, or RMSE, gives greater weight to large prediction errors.

This is important because major delivery-time inaccuracies may have a stronger negative impact on customer satisfaction.

### R² Score

The R² score measures the proportion of variation in delivery time explained by the model.

It will be interpreted together with MAE and RMSE because it does not express prediction error directly in minutes.

### Mean Absolute Percentage Error

Mean Absolute Percentage Error, or MAPE, expresses prediction error as a percentage.

MAE and RMSE will be treated as the primary evaluation metrics.

Additional analysis may report the percentage of predictions that fall within:

* ±5 minutes
* ±10 minutes

## Risk Analysis

Several risks may affect the reliability and generalizability of the project:

* Data leakage
* Missing or inconsistent values
* Poor data quality
* Limited feature engineering
* Categorical imbalance
* Model overfitting
* Large errors under difficult traffic or weather conditions
* Limited generalization to future delivery conditions

The following methods will be used to reduce these risks:

* Auditing features for possible target leakage
* Keeping the test set untouched until final evaluation
* Fitting preprocessing operations only on training data
* Applying cross-validation where appropriate
* Using regularization
* Using early stopping
* Performing hyperparameter tuning
* Evaluating difficult delivery scenarios separately
* Comparing multiple regression metrics

## Expected Outcomes

The project is expected to produce:

* A cleaned and processed food-delivery dataset
* Reusable preprocessing and feature-engineering pipelines
* A comparison of multiple regression models
* A trained delivery-time prediction model
* An analysis of the most influential features
* Visualizations of model performance
* A documented and reproducible machine learning workflow

## Limitations

The dataset is static and may not fully represent future delivery conditions.

Model performance may also vary under unusual circumstances such as:

* Severe weather
* Heavy traffic
* Unexpected restaurant delays
* Changes in delivery operations
* New geographic regions

Strong average performance may hide large errors in difficult delivery cases. Therefore, model evaluation will include both overall metrics and error analysis across different delivery conditions.

## Project Status

This project is currently under development.

## Author

**Cahide Tuncer**
**Anna Phan**



