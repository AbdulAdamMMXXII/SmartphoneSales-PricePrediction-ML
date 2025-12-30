# 📱 Smartphone Sales Price Prediction  
A supervised machine learning project for predicting smartphone selling prices using the **Smartphones Sales Dataset** from Kaggle. 
This repository contains the full workflow, including EDA, preprocessing, modelling, evaluation and visualisations.

---

## 📊 Project Overview  
This project investigates how smartphone specifications and commercial attributes influence selling price. 
Using regression techniques, the goal is to build accurate predictive models and analyse which features contribute most to pricing behaviour.

The workflow includes:
- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Feature engineering
- Regression modelling (Linear Regression & Random Forest)
- Hyperparameter tuning (GridSearchCV)
- Cross‑validation
- Model comparison and evaluation

---

## 📁 Dataset  
**Source:** Kaggle – Smartphones Sales Dataset  
Link: https://www.kaggle.com/datasets/yaminh/smartphone-sale-dataset/data  

**Dataset Size:**  
- 3,114 rows  
- 12 attributes  

**Key Features:**  
- Brand, Model, Colour  
- Memory (RAM), Storage  
- Rating  
- Original Price, Selling Price  
- Discount & Discount Percentage  

---

## 🧹 Data Preprocessing  
The following transformations were applied:

### ✔ Missing Value Handling  
- **Memory & Storage:** Mode imputation  
- **Rating:** Mean imputation  

### ✔ Data Cleaning  
- Extracted numeric values from RAM/Storage (e.g., “8GB” → 8)  
- Converted categorical features using Label Encoding  

### ✔ Scaling  
- StandardScaler applied to numerical features for model stability  

### ✔ Feature Engineering  
- Created new features such as total discount impact  

---

## 🔍 Exploratory Data Analysis  
EDA included:  
- Distribution plots (histograms, boxplots)  
- Outlier inspection  
- Correlation heatmaps  
- Scatter plots for price relationships  
- Analysis of brand influence and discount behaviour  

---

## 🤖 Machine Learning Models  

### **1. Linear Regression (Baseline)**  
- Simple, interpretable model  
- Captures linear relationships  
- Useful for benchmarking  

### **2. Random Forest Regressor (Primary Model)**  
- Handles non‑linear interactions  
- Robust to outliers  
- Provides feature importance  

---

## ⚙️ Hyperparameter Tuning  
GridSearchCV was used to optimise Random Forest parameters:
Best parameters achieved:{'n_estimators': 200, 'max_depth': None, 'min_samples_split': 2}


**Model Evaluation**
Metrics Used:
MAE (Mean Absolute Error)

RMSE (Root Mean Squared Error)

R² Score

Summary:
Model	MAE	RMSE	R²
Linear Regression	~2500	~3000	~0.65
Random Forest	~1800	~2200	~0.82
Random Forest (Tuned)	145.9	439.7	0.9998
Random Forest significantly outperformed Linear Regression.

🔁 Cross‑Validation
5‑fold CV was applied to validate model robustness.

Linear Regression: Mean R² = 1.0

Random Forest: Mean R² ≈ 0.9981

📈 Visualisations
The notebook includes:

Histograms

Boxplots

Correlation heatmaps

Actual vs Predicted scatter plots

Cross‑validation boxplots

Comparative bar charts (MAE/RMSE)

🧠 Key Insights
Original Price is the strongest predictor of Selling Price

Discounts influence price but do not change overall pricing trends

RAM and Storage have moderate impact

Brand has limited influence compared to technical specifications

🚀 Future Improvements
Add advanced models (XGBoost, SVR)

Expand feature engineering

Include time‑series pricing trends

Apply SHAP for model explainability
