# 🔹 Sabriya Sowers' Linear Regression Housing Analysis 🔹

**Author:** Sabriya Sowers  
**Date:** October 23, 2025  
**Objective:** Predict the median house price in California using available housing features.

---

## 🧭 Overview
This project builds a **Linear Regression** model to predict **median house value** in California based on features such as median income, average number of rooms, and house age.  
It demonstrates the complete data science workflow — from loading and exploring data to training and evaluating a regression model.

---

## 📦 Technologies Used
- Python 3.x  
- pandas, NumPy  
- seaborn, matplotlib  
- scikit-learn (sklearn)

---

## 📊 Dataset
The dataset used is the **California Housing Dataset**, provided by `sklearn.datasets.fetch_california_housing`.

**Dataset Summary**
- **Instances:** 20,640  
- **Features:** 9 numeric attributes  
- **Target:** `MedHouseVal` (Median House Value)

**Features include:**
1. `MedInc` – Median income in block group  
2. `HouseAge` – Median house age  
3. `AveRooms` – Average number of rooms per household  
4. `AveBedrms` – Average number of bedrooms per household  
5. `Population` – Population of block group  
6. `AveOccup` – Average number of household members  
7. `Latitude` – Block group latitude  
8. `Longitude` – Block group longitude  
9. `MedHouseVal` – Target variable  

No missing values or data quality issues were found.

---

## 🔍 Workflow Summary

### **1️⃣ Data Loading and Exploration**
- Loaded dataset using `fetch_california_housing(as_frame=True)`
- Converted to a pandas DataFrame
- Explored data using:
  - `info()` for data types  
  - `describe()` for summary stats  
  - `isnull().sum()` to check missing values  

---

### **2️⃣ Data Visualization**
Visualized feature distributions using:
- **Histograms** (`data_frame.hist()`)
- **Boxenplots** (via seaborn)
- **Pairplots** (`sns.pairplot()`) to explore correlations between features

---

### **3️⃣ Feature Selection**
Selected the following predictors and target for model training:
- **Predictors (X):** `MedInc`, `AveRooms`  
- **Target (y):** `MedHouseVal`

---

### **4️⃣ Model Training**
- Split data into training (80%) and testing (20%) sets using:
  ```python
  train_test_split(X, y, test_size=0.2, random_state=42)

## Notebook Link
[View Full Notebook on GitHub →](https://github.com/ssowers2/applied-ml-sowers/blob/main/notebooks/project01/ml01.ipynb)