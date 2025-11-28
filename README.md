Here is a **clean, polished, GitHub-ready README.md** version of your content.
I’ve fixed formatting, grammar, structure, math notation, and made it professionally presentable.

---

# 🔧 Prediction of Final Tempered Hardness (HRC)

A **physics-informed machine learning framework** for predicting the **final tempered hardness** of alloy steels using chemical composition, heat-treatment parameters, and metallurgy-based engineered features.

This project demonstrates how combining domain knowledge with modern ML algorithms can significantly improve prediction accuracy for heat-treating outcomes.

---

## 📘 Overview

The goal of this project is to build a machine learning model that predicts **final hardness after tempering** based on:

* Steel chemistry
* Tempering temperature & time
* Initial quenched hardness
* Physics-informed engineered features (HJP, CE, PCM, etc.)

The developed models achieve:

| Model             | R²         | RMSE (HRC) |
| ----------------- | ---------- | ---------- |
| **Random Forest** | 0.9846     | 1.73       |
| **XGBoost**       | **0.9884** | **1.50**   |

XGBoost provides the best performance and shows strong robustness against overfitting.

---

## 📂 Dataset Description

Each row in the dataset represents a steel sample with:

### **1. Chemical Composition (wt%)**

`C, Mn, Si, Cr, Mo, Ni, V, Cu` and additional alloying elements where available.

### **2. Heat Treatment Parameters**

* **Tempering Temperature** (°C)
* **Tempering Time** (seconds)
* **Initial Hardness after Quenching** (HRC)
* **Final Tempered Hardness** (HRC — *target variable*)

### **3. Categorical**

* **Steel Group** (one-hot encoded)

---

## 🧪 Feature Engineering (Physics-Informed)

This project uses metallurgy-driven engineered features to improve model interpretability and accuracy.

### **1. Hollomon–Jaffe Parameter (HJP)**

Represents tempering severity based on diffusion kinetics:

```
HJP = T(K) × [20 + log10(t in hours)]
```

---

### **2. Carbon Equivalent (CE – IIW)**

Weldability / hardenability indicator:

```
CE = C + Mn/6 + (Cr + Mo + V)/5 + (Ni + Cu)/15
```

---

### **3. PCM (JWES Carbon Equivalent)**

More sensitive for low-carbon steels:

```
PCM = C + Si/30 + Mn/20 + Cu/20 + Ni/60 + Cr/20 + Mo/15 + V/10
```

---

### **4. Hardenability Index (HI)**

```
HI = C + (Mn + Cr + Mo + V)/5 + Ni/10
```

---

### **5. Carbide Former Index (CFI)**

```
CFI = Cr + Mo + V
```

---

### **6. log(Time)**

Captures nonlinear tempering kinetics (diffusion-controlled reaction rate).

---

### **7. One-hot Encoded Steel Groups**

Enables the model to learn steel-family-specific tempering responses.

---

## 🤖 Machine Learning Models

### **🔹 Random Forest Regression**

* 500 trees
* `max_features="sqrt"`
* **R² = 0.9846**
* **RMSE = 1.73 HRC**

---

### **🔹 XGBoost Regression (Best Performing Model)**

* `n_estimators = 800`
* `max_depth = 6`
* `learning_rate = 0.03`
* **R² = 0.9884**
* **RMSE = 1.50 HRC**

XGBoost outperforms RF due to its depth-wise tree boosting and regularization, making it more resistant to overfitting.

---

## 📌 Key Highlights

* Physics-informed features significantly improve predictive accuracy
* Final hardness can be predicted within **±1.5 HRC**
* Strong generalization across multiple steel groups
* Useful for heat-treatment optimization, industrial QC, and alloy design

---

If you want, I can also:

✅ Generate badges (Python version, license, model accuracy)
✅ Add a Usage / Installation section
✅ Add sample code for training the model
✅ Create a project structure layout
✅ Generate visualizations for the README

Just tell me!
