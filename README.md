# Cars4You: Car Price Prediction

> **Machine Learning Project (2025/2026)** designed to predict vehicle market prices using regression techniques.

---

## Project Overview
**Cars 4 You** is a car resale company that wants to optimize its vehicle evaluation process. Currently, the process requires physical inspections by mechanics, which creates bottlenecks.

**The Goal:** Develop a Machine Learning model to estimate the price of a car based on its characteristics (mileage, brand, fuel type, etc.) without needing a physical check-up.

---

## Dataset
The dataset consists of records from the company's database, including features such as:
* `brand`: Manufacturer of the car.
* `fuel_type`: Diesel, Petrol, Electric, etc.
* `mileage`: Distance traveled.
* `engine_size`: Capacity of the engine.
* `transmission`: Automatic or Manual.
* **Target Variable:** `price` (in Euros).

---

## Tech Stack
The project was developed using Python and the following libraries:

| Library | Usage |
| :--- | :--- |
| **Pandas** | Data Manipulation & Aggregation |
| **Matplotlib / Seaborn** | Data Visualization (EDA) |
| **Scikit-Learn** | Data Preprocessing & Modeling |
| **XGBoost** | Gradient Boosting for Regression |
| **SciPy** | Statistical Analysis |

---

## Project Pipeline

The project followed a standard Data Science workflow:

1.  **Data Cleaning** 
    * Handling missing values.
    * Removing duplicates.
    * Outlier detection (IQR method).

2.  **Exploratory Data Analysis (EDA)** 
    * Univariate analysis (Distributions).
    * Bivariate analysis (Correlation with Price).
    * Feature Importance visualization.

3.  **Feature Engineering** 
    * Encoding categorical variables (One-Hot & Target Encoding).
    * Feature scaling (StandardScaler).

4.  **Model Building** 
    * Linear Regression (Baseline).
    * Random Forest Regressor.
    * **XGBoost Regressor (Best Model)**.

---

## Key Results
Here is a snapshot of our model's performance on the validation set:

| Metric | Score |
| :--- | :--- |
| **RMSE** | *1234.56 €* (Substitui pelo teu valor) |
| **R² Score** | *0.89* (Substitui pelo teu valor) |

> **Visual Insight:**
> 
> ![Model Results](images/feature_importance.png)

---

## Team Members (Group 08)
This project was created by:

**Giancarlo Pugliese** (20250533)
**Leonor Laborinho** (20250469)
**Rita Rodrigues** (20250528)
**Vasco Líbano Monteiro** (20250478)

---
<p align="center">
  <i>Created for the Machine Learning Course Assessment.</i>
</p>
