# Sales Forecast project

This document provides a detailed workflow of the Iron Kaggle project, focusing on predicting future sales for a retail chain using historical sales data. The project follows a structured approach, incorporating data preprocessing, exploratory data analysis (EDA), feature engineering, machine learning modeling, and evaluation against actual sales. Specific libraries, file names, and steps are highlighted below.

## Step 1: Importing Libraries and Reading Data

The project starts with importing necessary Python libraries:

- `pandas` and `numpy` for data manipulation,
- `seaborn` and `matplotlib.pyplot` for visualization,
- custom `eda_functions.py` for exploratory data analysis.

Data is read from two Excel files:

- **Past sales data:** `Past_Data.xlsx`, containing historical sales information.
- **Future sales data:** `Future_data_without_label.xlsx`, intended for making sales predictions.

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from eda_functions import standard_head, analyze_data
```

## Step 2: Initial Data Analysis

Using `pandas`, the datasets are loaded and initially analyzed to understand their structure, using custom functions from `eda_functions.py` for summarizing and analyzing the data. This step is crucial for planning the preprocessing and modeling strategy.

## Step 3: Data Cleaning and Preparation

Data cleaning involves creating new date-related columns (`month`, `year`, `week`, `day`) using `pandas`' datetime functionality and filtering out rows irrelevant for modeling (e.g., days when stores were closed). This step ensures the data is in the right format for analysis and modeling.

## Step 4: Exploratory Data Analysis (EDA)

EDA is conducted to uncover sales trends and factors influencing sales, utilizing `seaborn` and `matplotlib` for visualization. Insights from this phase guide the feature engineering and modeling steps.

## Step 5: Feature Engineering

New features are created to enrich the models, including interactions between customers and promotions, categorization of customer numbers, and calculation of average payments by customers. This process leverages `numpy` and `pandas` for data manipulation, enhancing the dataset with information believed to improve model predictions.

## Step 6: Machine Learning Modeling

Several machine learning models are evaluated:

- **Linear Regression**, **Decision Tree**, **Random Forest**, and **CatBoost** from `sklearn` and `catboost` libraries.
- Models are trained on the historical data (`Past_Data.xlsx`) and evaluated using metrics like RMSE, MAE, and R-squared to select the best performer.

```python
from sklearn.linear_model import LinearRegression
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor
from catboost import CatBoostRegressor
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score
```

## Step 7: Preparing and Exporting Predictions

The final model predictions are prepared for the future dataset (`Future_data_without_label.xlsx`) and exported to an Excel file named `predictions_4.xlsx`. This step involves merging predictions with the future dataset template and ensuring the format aligns with project requirements.

## Step 8: Evaluation Against Actual Sales

After appending the actual sales to the `predictions_4.xlsx` file, the model's predictions are evaluated against these actual figures using:

- **RMSE:** 493
- **MAE:** 306
- **R-squared (R2):** 0.985

This evaluation confirms the model's accuracy and effectiveness in predicting future sales, showcasing the project's success in achieving its objective. The `pandas` library is utilized for data manipulation during this final evaluation phase, with metrics calculated using functions from the `sklearn.metrics` module.

## Conclusion

The Iron Kaggle project illustrates a comprehensive approach to sales forecasting, from data preprocessing and exploration through to predictive modeling and evaluation. By carefully selecting features, employing a variety of modeling techniques, and rigorously assessing performance, the project achieves a high degree of accuracy in predicting future sales, demonstrating the potential of data science in retail sales forecasting.
