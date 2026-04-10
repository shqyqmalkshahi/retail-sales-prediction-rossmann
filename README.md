# retail-sales-prediction-rossmann
Built a machine learning model to predict daily retail sales using the Rossmann dataset, improving forecasting accuracy to reduce overstock and stockouts.

# Retail Sales Prediction (Rossmann Dataset)

## Overview
This project develops a machine learning model to predict daily retail sales across Rossmann stores in Germany. The goal is to improve demand forecasting accuracy, enabling better inventory planning, reduced overstock, and prevention of stockouts.

The project follows a full data science workflow, including exploratory analysis, feature engineering, model development, and evaluation.

---

## Problem Statement
Retail businesses rely on accurate demand forecasts to optimize inventory, staffing, and promotions. Poor predictions can lead to:

- Overstock → increased storage costs and waste  
- Stockouts → lost sales and poor customer experience  

This project addresses this challenge by building a predictive model that captures temporal patterns, promotional effects, and store-level differences.

---

## Business Context
The model is designed for:

- Store managers → optimize daily inventory decisions  
- Supply chain teams → improve distribution planning  
- Corporate planners → align promotions with demand  

Even small improvements in forecast accuracy (1–2%) can significantly reduce operational costs and improve customer satisfaction :contentReference[oaicite:1]{index=1}  

---

## Dataset
- Source: Rossmann Store Sales dataset (Kaggle)  
- ~1,000 stores  
- Daily data from 2013–2015  

### Data Components
- `train.csv` → daily sales and date-level features  
- `store.csv` → store-level metadata  

### Features
- Promotions (Promo, Promo2)  
- Competition (distance, open time)  
- Store type and assortment  
- Temporal features (date, weekday, seasonality)  

---

## Methodology

### Data Preparation
- Merged `train.csv` and `store.csv` on Store  
- Removed leakage-prone variables (Customers, Open)  
- Handled missing values:
  - Competition distance → median  
  - Promo/competition fields → default values  
- Converted date into structured features  

### Feature Engineering
- Time-based features:
  - Year, Month, Day, WeekOfYear  
- Competitive features:
  - CompetitionOpen (months since competitor opened)  
- Promotion features:
  - IsPromo2Month (active promotion periods)  
- One-hot encoding for categorical variables  

---

## Models Used

### Random Forest Regressor (Final Model)
- Tuned max_depth = 20  
- Best performance across models  

### Decision Tree Regressor
- Depth = 20  
- Strong performance but slightly less accurate  

### XGBoost Regressor
- Good performance but slower and less effective than Random Forest  

---

## Results

| Model | R² Score | RMSE | MAE |
|------|---------|------|------|
| Random Forest | **0.8589** | 1256.89 | 891.32 |
| Decision Tree | 0.8011 | 1567.42 | 1104.55 |
| XGBoost | 0.7000 | 1693.01 | 1237.15 |

👉 Random Forest was selected as the final model due to its strong generalization and balanced performance :contentReference[oaicite:2]{index=2}  

---

## Key Insights

- Promotions have a strong positive impact on sales  
- Day-of-week patterns significantly influence demand  
- Store characteristics (type, assortment) affect performance  
- Tree-based models effectively capture nonlinear relationships  
- Feature engineering significantly improved model accuracy  

---

## Model Evaluation

- R² Score: **0.8589**  
- RMSE: significantly reduced after tuning  
- MAE: relatively low, indicating stable predictions  

The model demonstrates strong predictive capability and is suitable for operational forecasting.

---

## Deployment Readiness

The model is suitable for deployment with:

- Daily batch prediction pipeline  
- Periodic retraining with new data  
- Monitoring for data drift and performance degradation  

---

## Business Value

- Improves inventory planning accuracy  
- Reduces stockouts and overstock  
- Supports data-driven retail decisions  
- Enhances operational efficiency across stores  

---

## Limitations

- No lag-based time-series features included  
- External factors (weather, holidays) not incorporated  
- Model trained on historical data only  

---

## Future Improvements

- Add lag and rolling features (e.g., last 7/30 days sales)  
- Incorporate external data (weather, holidays)  
- Explore time-series models (ARIMA, Prophet)  
- Perform feature importance analysis  

---

## Project Structure

- `.ipynb` → data analysis and modeling  
- `.pdf` → full project report  
- `images/` → visualizations  

---

## Tools Used

- Python  
- pandas  
- numpy  
- scikit-learn  
- matplotlib / seaborn  
- Jupyter Notebook  

---

## Author
Shaghayegh Malekshahi  
Master’s in Data Science  
