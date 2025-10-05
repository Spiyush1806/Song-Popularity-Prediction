# Song-Popularity-Prediction
UMC 301 Kaggle Assignment-1


This notebook is my submission for the UMC301 Kaggle Assignment - 1.
Before running the code, please adjust the file paths as this notebook was originally executed on ubuntu (Vscode).


## 🧠 Methodology

**Imputation:** Performed using **MICE (Multiple Imputation by Chained Equations)** with `IterativeImputer` on the train and test data separately to avoid data leakage. 

**Feature Engineering:** Created extensive interaction and polynomial features, including ratios, logarithmic transformations, squared terms, and binned versions of numerical attributes (e.g., energy, loudness, tempo).  

**Modeling:** Trained three boosting-based classifiers — **HistGradientBoosting**, **LightGBM**, and **XGBoost** — using **Stratified K-Fold Cross Validation (n=5)** for robust model evaluation.  

**Evaluation:** Used **ROC-AUC** as the main performance metric to assess each model’s discriminative ability.  

**Ensembling:** Combined model outputs using a **weighted average ensemble**, where each model’s contribution was proportional to its CV AUC score.  

**Stacking (Meta-Model):** If LightGBM and XGBoost were both available, built a **meta-model** using **Logistic Regression** to stack out-of-fold predictions and enhance performance.  

**Output:** Generated and saved multiple submissions — individual model predictions, a weighted ensemble submission, and a stacked meta-model submission for final evaluation.

