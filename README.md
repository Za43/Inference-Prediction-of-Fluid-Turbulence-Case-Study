# Inference & Prediction of Fluid Turbulence

### Authors: Khushmeet Chandi, Athena Ru, Jason Ren, Zaid Muqsit  
**Date: 2023-10-28**

## Project Overview

This project focuses on analyzing particle cluster distributions in fluid turbulence using various statistical models. The dataset comprises 89 simulations, characterized by three predictors:
- **Reynolds Number (Re)**: Represents particle tracking resolution.
- **Froude Number (Fr)**: Represents gravitational acceleration.
- **Stokes Number (St)**: Represents particle characteristics.

The response variables are the four raw moments: mean (E[X]), variance (E[X²]), skewness (E[X³]), and kurtosis (E[X⁴]).

The objective is to perform inference and prediction of the particle cluster volume distributions under varying environmental conditions.

## Data and Preprocessing

The dataset includes 89 simulations of particle clusters under different fluid turbulence conditions. Key preprocessing steps include:
- Log transformations to normalize the moments and predictors.
- Multicollinearity checks to ensure appropriate model usage.
- Feature engineering with interaction terms based on domain insights.

## Models

### 1. **First Moment Model (Mean Volume)**
A linear regression model with interaction effects between Reynolds Number and Froude Number to predict mean particle cluster volume.

### 2. **Second Moment Model (Variance)**
Lasso regression was used for variable selection. This model predicts variance in particle cluster volume, considering both main effects and interaction terms.

### 3. **Third Moment Model (Skewness)**
A linear regression with interaction effects was used, providing insights into how fluid turbulence affects the skewness of particle distributions.

### 4. **Fourth Moment Model (Kurtosis)**
This model includes interaction terms and investigates how gravitational acceleration and Reynolds Number affect the tail behavior of the distribution.

## Key Findings

- **Reynolds Number** has a significant negative impact on the first moment (mean volume) of particle clusters.
- **Froude Number** influences the distribution, with stronger gravitational forces leading to decreased variance and kurtosis.
- Interaction terms between Reynolds Number and Froude Number suggest complex dynamics in how turbulence influences particle clustering.

## Methodology

We applied multiple regression techniques including:
- **Linear Regression**: For the first moment model.
- **Ridge & Lasso Regression**: For variable selection and regularization to prevent overfitting.
- **Nested Cross-Validation**: To evaluate model performance and tune hyperparameters.

The models were evaluated using metrics like **Root Mean Square Error (RMSE)** and **Adjusted R²** to determine their predictive accuracy.

## Results

- **Model Performance**: All models had adjusted R² values above 0.92, indicating high explanatory power.
- **RMSE**: The 5-fold cross-validated RMSE for each model was low, confirming the robustness of the predictions.

## Visualizations

The repository includes several visualizations, such as:
- **Histograms of Log-Transformed Moments**
- **Scatter plots of Moment Predictions vs. Predictors**
- **Residual and QQ Plots** for model validation
