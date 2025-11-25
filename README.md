# Used Car Price Drivers Project

## Project Overview
This project analyzes a dataset of ~426,000 used vehicles to understand **what factors most influence used car prices** and to build **predictive machine learning models** capable of estimating sale price.  
The work follows the **CRISP-DM** methodology and demonstrates the use of **multiple regression models** including both linear and advanced ensemble approaches.

The analysis is structured into two Jupyter Notebooks:
1. **Data Preparation & Exploratory Analysis Notebook**: https://github.com/ANCAMABEBA/Module11/blob/main/VehiclesPricesDataPrep.ipynb
2. **Modeling & Machine Learning Notebook** 

---

## Data 
In this application, we will explore a dataset from Kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure the speed of processing. https://github.com/ANCAMABEBA/Module11/blob/main/Data/practical_application_II_starter.zip

---

## Business Goal
To support a used-car dealership in optimizing pricing and inventory decisions by identifying:
- The **main drivers of vehicle price**
- **Feature combinations** that increase resale value
- Clear, actionable **business insights and recommendations**

---

## Key Findings & Insights

### Predictive Model Performance Summary
| Model | RMSE ↓ | R² ↑ | Notes |
|--------|-----------|-----------|-----------|
| Baseline Linear Regression | 12,127 | 0.368 | weak explanatory power |
| Sequential Feature Selection (15 features) | 12,402 | 0.339 | more interpretable, lower accuracy |
| Ridge / Lasso | ~12,000 | ~0.36 | no major improvement |
| **Random Forest Regressor** | **6,337** | **0.827** | best predictive performance |
| **XGBoost Regressor** | **7,221** | **0.776** | strong, but below RF |

### What Drives Car Prices?
Top predictors identified:
- **Vehicle Year** — newer models significantly increase price
- **Mileage (Odometer)** — strong negative impact
- **Vehicle Type** — pickups, trucks, and performance cars retain value
- **Fuel Type** — diesel vehicles have higher price contribution
- **Title Status & Condition** — clean titles and high condition matter
- **Region** — pricing varies significantly across U.S. regions

### Random Forest Advantages
- Captures **nonlinear pricing relationships**
- Handles complex interactions among features
- Produces **high predictive accuracy**

### XGBoost Advantages
- Highly tunable ensemble method
- Works well with **SHAP explainability**
- Strong nonlinear modeling performance

---

## 📁 Repository Structure
