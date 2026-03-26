# retail-sales-prediction-rossmann
Built a machine learning model to predict retail store sales using the Rossmann dataset, improving forecasting accuracy to reduce overstock and stockouts.

# Retail Sales Prediction (Rossmann Dataset)

##  Overview
This project builds a machine learning model to predict daily retail sales across Rossmann stores in Germany. The goal is to improve inventory planning, reduce overstock, and prevent stockouts.

---

##  Problem Statement
Retail businesses need accurate demand forecasting to optimize inventory, staffing, and promotions. Poor predictions lead to lost sales or excess costs.

---

##  Dataset
- Rossmann Store Sales (Kaggle)
- ~1,000 stores
- Daily data (2013–2015)
- Includes promotions, competition, and store features

---

##  Methods
- Data cleaning and preprocessing
- Feature engineering:
  - Time-based features (Year, Month, Day)
  - Competition duration
  - Promotion indicators
- One-hot encoding for categorical variables

---

##  Models Used
- Random Forest Regressor (final model)
- Decision Tree
- XGBoost

---

##  Results
- Best model: Random Forest
- R² Score: **0.8589**
- RMSE: significantly improved after tuning

---

##  Key Insights
- Promotions strongly impact sales
- Day-of-week patterns are significant
- Store characteristics influence performance
- Tree-based models capture nonlinear relationships effectively

---

##  Business Value
- Improves inventory planning
- Reduces stockouts and overstock
- Supports data-driven retail decision making

---

##  Future Improvements
- Add time-series features (lags, rolling averages)
- Incorporate weather data
- Explore advanced forecasting models

---

##  Author
Shaghayegh Malekshahi  
Master’s in Data Science – Bellevue University
