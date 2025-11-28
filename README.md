# Prediction-Of-Final-Hardness
Tempering Hardness Prediction using Machine Learning

A physics-informed ML model for predicting tempered hardness of alloy steels

This project develops a machine learning framework to predict the final tempered hardness (HRC) of alloy steels based on:
1. Chemical composition
2. Heat-treatment parameters
3. Metallurgy-informed engineered features

The models achieve high accuracy (R² ≈ 0.985–0.989, RMSE ≈ 1.5 HRC) using Random Forest and XGBoost.

Dataset -------------------

Each row represents a steel sample with:
- Composition (wt%)
C, Mn, Si, Cr, Mo, Ni, V, Cu and other alloying elements.

- Heat Treatment Parameters
  
Tempering temperature (°C)

Tempering time (seconds)

Initial hardness (HRC) after quenching

Final tempered hardness (target)

- Categorical
Steel group (one-hot encoded)


Feature Engineering ----------

This project uses physics-informed engineered features, including:

1. Hollomon–Jaffe Parameter (HJP)

Captures tempering severity via diffusion kinetics:

𝐻𝐽𝑃 = 𝑇(𝐾)*[20+log10(𝑡 in hours)]

2. Carbon Equivalent (CE – IIW)

CE = C + (Mn/6) + ((Cr + Mo + V)/5) + ((Ni + Cu)/15)

4. PCM (JWES Carbon Equivalent)

PCM = C + (Si/30) + (Mn/20) + (Cu/20) + (Ni/60) + (Cr/20) + (Mo/15) + (V/10)
​
6. Hardenability Index (HI)

HI = C + ((Mn + Cr + Mo + V)/5) + (Ni/10)

7. Carbide Former Index (CFI)

CFI = Cr + Mo + V

9. log(Time)

Captures nonlinear tempering behavior.

11. One-hot encoded steel groups

Models Used--------------

Random Forest Regression

1. 500 trees

2. max_features="sqrt"

3. Achieved R² = 0.9846, RMSE = 1.73 HRC

XGBoost Regression

1. n_estimators=800

2. depth=6, lr=0.03

3. Achieved R² = 0.9884, RMSE = 1.50 HRC


XGBoost performs slightly better and is more robust against overfitting.
