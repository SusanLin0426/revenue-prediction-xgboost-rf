# Revenue Prediction with XGBoost and Random Forest

This repository contains the implementation and analysis for predicting monthly revenue changes of Taiwanese listed companies using machine learning models. The project compares **XGBoost** and **Random Forest** under different preprocessing methods and investigates sector-specific performance (with a focus on the semiconductor industry).

---

## Project Structure
- `Revenue Changes Prediction.ipynb` : Jupyter Notebook with code implementation and analysis.
- `Revenue Changes Prediction.pdf` : Full report summarizing results, figures, and insights.

---

## Research Overview

### Objectives
1. Predict monthly revenue changes during **2017–2019** and **2020–2022**.  
2. Compare model performance across:
   - XGBoost vs. Random Forest  
   - Deflated vs. Original (non-deflated) data  
   - Semiconductor industry vs. all industries  
3. Analyze:
   - Feature importance  
   - Classification errors  
   - Impact of macro events (COVID-19, US-China trade war)  

### Methodology
- **Models:** XGBoost, Random Forest  
- **Preprocessing:**  
  - Removed companies with non-positive revenue  
  - Time-series formatting  
  - Deflation using rolling mean & standard deviation (t-48 to t-1)  
- **Evaluation:** Accuracy, feature importance ranking, error type distribution  

---

## Key Findings
- **XGBoost with deflation consistently outperforms** Random Forest and non-deflated data models.  
- Lagged variables such as **t-12, t-13, t-24** are more important than immediate lag (t-1).  
- Model accuracy is lower in **Q1 (Jan–Mar)** due to seasonal and holiday effects.  
- **COVID-19 (2020–2021)** and the **US-China trade war (2018)** significantly reduced prediction accuracy.  
- Semiconductor industry revenue is **less seasonal** than expected, indicating stronger sensitivity to macroeconomic shocks.  

---

## Example Results
- Best model: **XGBoost (Deflated, 2021-1)**  
- Worst model: **Random Forest (Original, 2020-2)**  
- Accuracy ranking:  
  `XGBoost_Deflate > RandomForest_Deflate > XGBoost_Original > RandomForest_Original`  

---

## Environment
- Python 3.9+  
- Jupyter Notebook  
- Libraries:  
  - `pandas`, `numpy`  
  - `scikit-learn`  
  - `xgboost`  
  - `matplotlib`, `seaborn`  
