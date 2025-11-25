# Used Car Price Drivers Project

## Project Overview
This project analyzes a dataset of ~426,000 used vehicles to understand **what factors most influence used car prices** and to build **predictive machine learning models** capable of estimating sale price.  
The work follows the **CRISP-DM** methodology and demonstrates the use of **multiple regression models** including both linear and advanced ensemble approaches.

The analysis is structured into two Jupyter Notebooks:
1. **Data Preparation & Exploratory Analysis Notebook:** https://github.com/ANCAMABEBA/Module11/blob/main/VehiclesPricesDataPrep.ipynb
2. **Modeling & Machine Learning Notebook:** https://github.com/ANCAMABEBA/Module11/blob/main/VehiclesPricesModeling.ipynb

---

## Data 
In this application, we will explore a dataset from Kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure the speed of processing. https://github.com/ANCAMABEBA/Module11/blob/main/Data/practical_application_II_starter.zip

---

## Business Goal
Important to keep in mind that goal is provide insoghts in pricing drivers rather than an accurate predictive model, this influenced our modeling decisions to prioritize interpretability.
To support a used-car dealership in optimizing pricing and inventory decisions by identifying:
- The **main drivers of vehicle price**
  - **Features** that increase resale value
  - **Features** that decrease resale value
- Clear, actionable **business insights and recommendations**

---

## Key Findings & Insights

### Predictive Model Performance Summary
| Model | RMSE ↓ | R² ↑ | Notes |
|--------|-----------|-----------|-----------|
| Baseline Linear Regression | 12,035 | 0.377 | weak explanatory power |
| Sequential Feature Selection (15 features) | 12,339 | 0.345 | more interpretable, lower accuracy |
| Ridge / Lasso | ~12,000 | ~0.37 | no major improvement |
| **Random Forest Regressor** | **6,147** | **0.837** | **best predictive performance** |
| Random Forest (Grid search hyperparameters) | ~12,000 | ~0.36 | no improvement |
| **XGBoost Regressor** | **6,895** | **0.795** | strong, but below RF |

---

## Model Scoring Criteria
Models performance were evaluated using these performance metrics:
  - **RMSE** measures the average size of prediction errors in the same units as the target variable (car prices), making it easy to interpret how far off our model is from real car prices and usefule for judging practical business value.
  - **R²** tells us what proportion of the variation in car prices is explained by the model, helping us to understand the model's overall explanatory power and how well it captures underlying drivers of price.


## What Drives Car Prices?
---
### Most Influential Drivers of Price

- **Year**  
  The single most important feature. Newer vehicles are consistently priced higher, reflecting normal depreciation patterns in the used-car market.

- **Odometer (mileage)**  
  The second strongest driver. Vehicles with lower mileage command higher prices; high mileage quickly erodes value.

- **Engine & Drivetrain Characteristics**  
  Features like **cylinders_clean**, **drive_fwd**, **drive_4wd** and related drivetrain indicators rank high, showing that performance and capability (power, towing, off-road use) significantly influence price.

- **Fuel Type (especially diesel)**  
  Diesel vehicles show higher importance, consistent with their role in heavy-duty, commercial, or high-torque applications that retain value longer.

- **Condition and Title Status**  
  **condition_numeric** and **title_numeric** contribute meaningfully, confirming that physical condition and a clean title both support higher pricing and buyer confidence.

- **Vehicle Type / Segment**  
  Features such as **type_pickup**, **type_truck**, **type_SUV**, and **type_sedan** appear in the top 20, indicating that the segment (work truck vs SUV vs sedan) is a clear price driver.

- **Regional Effects**  
  Some regional variables (e.g., **region_Pacific**, **region_Northeast**) show moderate importance, suggesting geographic variation in pricing, but they are less influential than age, mileage, and mechanical specs.

---

### Interpretation

Overall, the model shows that **core mechanical and structural characteristics** dominate price behavior:

- Newer, lower-mileage vehicles are worth more.  
- Performance-oriented configurations (more cylinders, 4WD/AWD, diesel) carry a price premium.  
- Vehicle segment (truck, pickup, SUV vs sedan) matters more than cosmetic attributes.

Paint colors, some transmission variations, and many minor categories have much lower importance, meaning they should play a secondary role in pricing decisions.

---

### Business Implications

For a used-car dealership, this analysis suggests:

- **Prioritize inventory** that is newer, low-mileage, and equipped with desirable powertrain and drivetrain options.
- **Use condition and title status** as key levers when evaluating trade-ins and auction purchases.
- **Treat color and minor attributes** as marketing preferences, not primary pricing drivers.
- Focus pricing and acquisition strategy around **year + mileage + segment + drivetrain + condition**, as these are the variables the model consistently identifies as most predictive of price.
---

## 📁 Repository Structure
