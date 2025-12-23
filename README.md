#**Housing Price Prediction (Machine Learning Project)**

**Project Overview**
This project builds a machine learning model to predict residential housing prices based on property characteristics such as square footage, number of bedrooms and bathrooms, year built, and city location. The goal is to demonstrate the end-to-end data science workflow, from data cleaning and feature engineering to model evaluation and prediction.

**Business Problem:**
Accurately estimating home prices is essential for buyers, sellers, and real estate professionals. Manual valuation methods are time-consuming and subjective. This project uses historical housing data to train a regression model that provides consistent and data-driven price predictions.

**Dataset**
- Source: Public housing dataset (CSV format)
- Observations: ~4,600 properties
- Numerical: bedrooms, bathrooms, square footage, floors, year built, etc.
- Categorical: city (one-hot encoded)

Data Cleaning & Feature Engineering
- Key preprocessing steps included:
- Dropping irrelevant or redundant columns
- Removing invalid entries (e.g., homes with zero bedrooms or bathrooms)
- Outlier removal using price-per-square-foot thresholds by city
- One-hot encoding city names
- Ensuring feature consistency between training and prediction

Modeling Approach:
Several regression models were evaluated:
- Linear Regression
- Lasso Regression
- Decision Tree Regressor
- Model selection was performed using cross-validation and GridSearchCV.
- Final Model
Linear Regression
Chosen for interpretability, stability, and strong cross-validated performance

Model Performance:
- R² Score: ~0.79
- Cross-Validation R²: ~0.80–0.83
This indicates the model explains approximately 79% of the variance in housing prices.

**Key Insights:**
- Square footage (sqft_living) is the strongest predictor of price
- Location (city) has a significant impact on housing value
- Bedroom count alone is less predictive when controlling for square footage
- Removing outliers significantly improved model stability

**Example Prediction:**
* predict_price('Seattle', sqft_living=800, bathrooms=1, bedrooms=1)
The model outputs a realistic estimated price based on learned patterns in the data.

**Limitations:**
The model assumes historical trends remain consistent
Does not account for market conditions, interest rates, or renovations beyond available features
Linear regression may not fully capture non-linear relationships

**Future Improvements:**
Use a Scikit-Learn pipeline for full preprocessing + modeling
Add feature scaling and regularization comparison
Deploy as a Streamlit web app
Incorporate additional location-based features (zip code clustering)

**Tools & Technologies:**
Python
Pandas, NumPy
Matplotlib
Scikit-Learn
Google Colab
