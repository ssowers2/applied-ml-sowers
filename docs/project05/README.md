# Project 05: Ensemble Machine Learning – Wine Quality Classification  

## Overview  
This project applies ensemble machine learning methods to the Red Wine Quality dataset. The goal is to evaluate how different ensemble approaches perform when predicting wine quality using chemical properties. The project includes data preparation, visualization, feature selection, model evaluation, model comparison, and conclusions. Ensemble models can improve accuracy and stability by reducing variance and combining the strengths of multiple algorithms. This project compares two ensemble methods: Random Forest and AdaBoost.

---

## Dataset  
**File:** `winequality-red.csv`  
**Rows:** 1,599  
**Columns:** 12 (11 chemical features + quality score)

The original quality score ranges from 0–10. For classification, the score was grouped into three classes:

- **0 – Low quality** (3–4)  
- **1 – Medium quality** (5–6)  
- **2 – High quality** (7–8)

Two new columns were created:
- `quality_label` – text version of the class  
- `quality_numeric` – numeric version used for modeling  

---

## Project Structure  

### 1. Import and Inspect the Data  
The dataset was loaded and inspected. No missing values were found, and all numeric columns were appropriate for modeling.

### 2. Data Preparation  
Steps included:
- Converting the quality score into low/medium/high categories  
- Encoding the numeric target variable  
- Creating visualizations:
  - Histogram of wine quality  
  - Boxplots of alcohol by quality  
  - Scatter plot of alcohol vs. volatile acidity  

These helped assess distributions and feature relationships.

### 3. Feature Selection  
All 11 chemical properties were used as features (`X`).  
The encoded target (`quality_numeric`) was used as the prediction target (`y`).  

Columns removed from features:
- `quality`  
- `quality_label`  
- `quality_numeric`  

These contain target information and would cause leakage if included.

### 4. Train/Test Split  
A stratified train/test split was used to maintain proportional class representation.

### 5. Model Training and Evaluation  
Two ensemble models were evaluated:

- **Random Forest (100 trees)**  
- **AdaBoost (100 estimators)**  

A helper function computed:
- Train/test accuracy  
- Train/test F1 score  
- Confusion matrices  

A results table was created, including gap calculations (train – test).

### 6. Comparison of Models  
A summary DataFrame includes:
- Accuracy  
- F1 scores  
- Overfitting gap metrics  

Random Forest performed the best overall.

### 7. Conclusions and Insights  
**Conclusions:**  
- Random Forest had the highest test accuracy (≈0.8875) and strongest F1 score.  
- It generalized well despite perfect training accuracy.  
- AdaBoost performed lower overall and was more sensitive to noisy samples.  

**Next Steps:**  
- Tune Random Forest hyperparameters (tree depth, number of trees).  
- Test an additional ensemble model such as Gradient Boosting.  
- Use cross-validation for more reliable performance estimates.  

**Comparison With Another Student:**  
- One student’s results were available for comparison.  
- Both analyses showed Random Forest outperforming other models.  
- Their results were slightly higher, but overall conclusions matched, showing the model’s consistency.

---

## Files Included  
- Jupyter Notebook containing full analysis  
- Data file (`winequality-red.csv`)  
- Generated visualizations

---