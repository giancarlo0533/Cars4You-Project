# Cars4You: Car Price Prediction Model

> **Machine Learning Project (2025/2026)** designed to predict vehicle market prices using regression techniques.

---

## Project Overview
**Cars 4 You** is a car resale company that wants to optimize its vehicle evaluation process. Currently, the process requires physical inspections by mechanics, which creates bottlenecks.

**The Goal:** Develop a Machine Learning model to estimate the price of a car based on its characteristics (mileage, brand, fuel type, etc.) without needing a physical check-up.

---

## Dataset
The dataset consists of records from the company's database, including features such as:
* `brand`: The car’s main brand (e.g. Ford, Toyota)
* `model`: The car model
* `year`: The year of Registration of the Car
* `tax`: The amount of road tax (in £) that, in 2020, was applicable to the car in question
* `mpg`: Average Miles per Gallon
* `previousOwners`: Number of previous registered owners of the vehicle.
* `hasDamage`:Boolean marker filled by the seller at the time of registration stating whether the car is damaged or not.
* `fuel_type`:Type of Fuel used by the car (Diesel, Petrol, Hybrid, Electric)
* `mileage`: The total reported distance travelled by the car (in miles)
* `engine_size`: Size of Engine in liters (Cubic Decimeters)
* `transmission`: Automatic or Manual.
* **Target Variable:** `price` (in Pounds).

---

## Tech Stack
The project was developed using Python and the following libraries:

| Library | Usage |
| :--- | :--- |
| **Pandas / NumPy** | Data Manipulation, Aggregation & Linear Algebra |
| **Matplotlib / Seaborn** | Data Visualization (EDA) |
| **Scikit-Learn** | Data Preprocessing & Modeling |
| **SciPy** | Statistical Analysis |
| **Ipywidgets** | Interactive Interface (Deployment Section)|

---

## Project Pipeline

The project followed a standard Data Science workflow:

1. **Data Cleaning & Exploratory Analysis**
   * Importing needed libraries
   * Importing Datasets
   * Exploratory Data Analysis
   * Initial Data Preparation
   * Visual Exploration After Data Clean-up

2.  **Train/Validation Split** 

3.  **Pre-processing and Feature Engineering** 
    * Treating Missing Values
    * Treating Outliers
    * Feature Engeneering
    * Visual Exploration after feature engeneering
    * Scaling the variables
    * Encoding the Variables

4.  **Feature Selection** 
    * Filter Methods
    * Wrapper Methods
    * Embedded Methods
    * Feature Selection Conclusion

5. **Modeling and Evaluation**
   * Initial Modelling and evaluation without tunning
   * Hyperparameter tuning
   * Final Ensemble Model

6. **Open-Ended Section**
   * Driver Identification:Feature Importance Analysis
   * Deployment: Analysis Interface
   * What-if Analysis: Depreciation Curve

7. **Kaggle Submission**

---
### Model Selection & Evaluation
We selected the **R² Score** and the RMSE as our primary evaluation metrics for the Car Price Prediction model. During the selection process, we rigorously filtered out overfitted models—specifically those exhibiting perfect training scores (R² ≈ 1.0 / MSE ≈ 0) but failing to generalize on validation data (yielding negative or poor scores). Consequently, the final list of viable models is as follows:

## Key Results
Following the initial benchmarking, we performed hyperparameter optimization using RandomizedSearchCV with a PredefinedSplit. This ensured all models were evaluated on the exact same validation set. We maintained the log(1+price) transformation strategy to stabilize the learning process for all models.

| Model | MAE | RMSE | R^2
| :--- | :--- | :--- | :--- |
| **Ridge Regression** |2248.98| 3924.33 | 0.8377 |
| **Bagged KNN** | 1374.62 | 2546.34| 0.9317 |
| **Bagged Decision Tree** | 1343.98 | 2516.55 | 0.9333 |
| **Random Forest** | 1346.10 | 2525.71 | 0.9328 |
| **HistGradientBoosting** | 1278.49 | 2262.53 | 0.9460 |
| **Extra Trees Regressor** |1379.06|2586.27|0.9295|


The optimization process significantly reshuffled the model rankings, highlighting the limitations of linear approaches on this dataset. Bagged KNN emerged as the superior model, offering the best balance of accuracy and stability, followed closely by HistGradientBoosting as the leading tree-based method.

## Final Model
To maximize predictive performance, we implemented a Weighted Blending Ensemble. Instead of a simple average, we learned optimal non-negative weights for our top three models using constrained Linear Regression on the validation set.

| Model | Assigned Weight | Validation MAE |
| :--- | :--- | :--- |
| **Bagged KNN** | 16.5% |1375|
| **HistGradientBoosting** | 83.5% |1278|

The ensemble achieved a lower validation MAE (~1,259) compared to the best single learner. While HistGradientBoosting remains the dominant driver, the complementary signal from the bagged models provided a consistent improvement in robustness and accuracy. Consequently, this weighted blend was adopted as the final solution.

## Team Members (Group 08)
This project was created by:

**Giancarlo Pugliese** (20250533)
**Leonor Laborinho** (20250469)
**Rita Rodrigues** (20250528)
**Vasco Líbano Monteiro** (20250478)

---
<p align="center">
  <i>Created for the Machine Learning Course at NOVA IMS.</i>
</p>
