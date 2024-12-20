# Predicting Movie Rental Durations

![DVD Image](dvd_image.jpg)

## Overview

This project aims to develop a regression model to predict the number of days a customer rents a DVD based on various features. The prediction helps the DVD rental company optimize inventory management, enhancing operational efficiency. The target is to achieve a Mean Squared Error (MSE) of less than 3 on the test set.

## Problem Statement

A DVD rental company needs an efficient model to predict rental durations to streamline inventory planning. Using historical data, the goal is to build and evaluate regression models that meet the MSE target.

## Dataset

The dataset `rental_info.csv` includes the following features:

- **`rental_date`**: The date and time the customer rented the DVD.

- **`return_date`**: The date and time the DVD was returned.

- **`amount`**: Amount paid by the customer for the rental.

- **`amount_2`**: Square of the `amount`.

- **`rental_rate`**: Rental rate of the DVD.

- **`rental_rate_2`**: Square of the `rental_rate`.

- **`release_year`**: Release year of the movie rented.

- **`length`**: Length of the movie in minutes.

- **`length_2`**: Square of the `length`.

- **`replacement_cost`**: Replacement cost of the DVD.

- **`special_features`**: Additional features (e.g., Deleted Scenes, Behind the Scenes).

- **`NC-17`, `PG`, `PG-13`, `R`**: Dummy variables for movie ratings.

## Key Steps

### 1. Data Preprocessing

- Created the target column `rental_length_days` from `rental_date` and `return_date`.

- Generated dummy variables for special features: `deleted_scenes` and `behind_the_scenes`.

- Removed features that leak target information or are unnecessary for the model, like `rental_date` and `return_date`.

### 2. Train-Test Split

- Split the dataset into training and testing sets with 20% data in the test set.

- Ensured reproducibility by setting a random state (`SEED=9`).

### 3. Model Training and Evaluation

- Trained several regression models, including:

  - Gradient Boosting Regressor (GBR)

  - Decision Tree Regressor

  - Linear Regression

  - Bagging Regressor

  - Random Forest Regressor

  - AdaBoost Regressor

- Performed hyperparameter tuning for GBR using `RandomizedSearchCV`.

- Evaluated models using MSE, cross-validation, and train-test performance consistency.

### 4. Feature Importance

Visualized feature importance using Gradient Boosting Regressor to interpret model decisions.

## Results

- The recommended model is **Gradient Boosting Regressor** with tuned hyperparameters:

  - **n_estimators**: Optimized between 94.

  - **max_depth**: Optimized between 8.

- Test MSE: 1.96 (Achieved below 3.0).

- No overfitting detected, as cross-validation MSE closely matches training MSE.

