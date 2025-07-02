# 🏠 Egypt House Prices Prediction (Random Forest Model)

This project aims to predict housing prices in Egypt using machine learning, specifically a Random Forest Regressor.

---

## 📂 Project Overview

- **Data Source**: `Egypt_Houses_Price.csv`
- **Goal**: Predict the house `Price` based on features such as `Area`, `Compound`, `Type`, `Furnished`, and `Level`
- **Approach**: Clean the dataset and use a Random Forest model for regression

---

## 🧹 Data Cleaning Process

The original dataset had a number of issues:
- Inconsistent formatting (e.g., `"ground"` vs. `"0"`, `"standalone villa"` vs. `"stand alone villa"`)
- Missing values in important fields (`Furnished`, `Level`)
- Placeholder values like `"unknown"` or `"highest"`

To handle this:
- Categorical text was standardized and stripped
- `"unknown"` values were replaced with `None`
- Missing values in `"Furnished"` and `"Level"` were predicted using decision tree classifiers trained on other columns
- Only rows with at most 1 missing value were retained for imputation

---

## 🧠 Model Training

- Used `RandomForestRegressor` from `scikit-learn`
- Features were one-hot encoded using `pd.get_dummies`
- The dataset was split: 80% training, 20% testing
- Evaluation metric: **Root Mean Squared Error (RMSE)**

---

## ⚠️ Limitations

Despite completing the full ML pipeline, the model achieved **low accuracy** due to:
- Noisy and inconsistently labeled data
- Possibly weak feature correlations with price
- No external data sources or feature engineering

This project remains useful as an end-to-end demonstration of:
- Handling real-world dirty datasets
- Building predictive models
- Understanding model limitations

