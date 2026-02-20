# 🔧 Post-Tempering Hardness Prediction using Machine Learning

## 📌 Overview
This project applies machine learning models to **predict final hardness (HRC) after tempering** of carbon and low-alloy steels based on compositional and process parameters.

The dataset consists of **1,466 experimental samples**, including tempering conditions and alloy composition.

---

## 📊 Dataset

**Target Variable**
- Final hardness (HRC) – post tempering

**Input Features (13)**
- Tempering time (s)
- Tempering temperature (ºC)
- C (%wt)
- Mn (%wt)
- P (%wt)
- S (%wt)
- Si (%wt)
- Ni (%wt)
- Cr (%wt)
- Mo (%wt)
- V (%wt)
- Al (%wt)
- Cu (%wt)

**Removed Columns**
- Source
- Steel type
- Initial hardness (post quenching)

---

## 🧠 Models Evaluated

| Model | Test R² | Cross-Val R² |
|------|---------|--------------|
| Linear Regression | 0.891 | 0.806 |
| SVR (with scaling) | — | 0.652 |
| Random Forest (max_depth=10) | **0.978** | **0.900** |

✅ **Random Forest Regressor** achieved the best performance.

---

## ⚙️ Methodology

1. Data preprocessing and cleaning  
2. Train-test split (80/20)  
3. Feature scaling (StandardScaler where applicable)  
4. Model training  
5. 5-fold cross-validation  
6. Error evaluation  

---

## 📉 Error Metrics (Random Forest)

- **MAE:** 0.924 HRC  
- **RMSE:** 1.418 HRC  

---

## 🔍 Model Interpretability

SHAP (SHapley Additive exPlanations) was used to:

- Identify important features  
- Understand alloying element influence  
- Analyze tempering parameter effects  

---

## 🛠️ Libraries Used

- pandas  
- scikit-learn  
- matplotlib  
- seaborn  
- shap  

---

## 🚀 Key Outcome

Random Forest successfully captures **nonlinear relationships** between:

- Tempering conditions  
- Steel composition  
- Final hardness  

This demonstrates the effectiveness of ML for materials property prediction.

---
