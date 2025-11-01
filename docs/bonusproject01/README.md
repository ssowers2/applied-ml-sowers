# Bonus Project: Wine Data Classification

**Author:** Sabriya Sowers  
**Date:** October 31, 2025  

## Project Overview
This bonus project extends the Titanic analysis by applying similar data exploration and modeling techniques to the **Wine Dataset** available in `scikit-learn`.  
The dataset includes 178 samples of wines, each measured across 13 chemical features (e.g., alcohol content, color intensity, phenolic compounds).  
The goal is to explore the data, visualize relationships, and identify which variables best distinguish between the three wine classes.

---

## Goals
- Inspect and verify data quality (missing values, duplicates, and data types)  
- Rename columns for readability and interpretability  
- Explore feature relationships using histograms, scatter plots, and correlation heatmaps  
- Identify top predictive features  
- Compare class balance using basic and stratified splits  
- Reflect on how chemical and visual properties influence wine classification

---

## Dataset
The dataset contains **13 numeric features** and a **target variable (`wine_class`)** that identifies each wine’s category (0, 1, or 2).  
There are no missing values or duplicates, and all data types are numeric.

**Example renamed features:**
| Original Name | Renamed Column |
|----------------|----------------|
| `hue` | `color_hue` |
| `od280/od315_of_diluted_wines` | `phenolic_ratio` |
| `alcohol` | `alcohol_pct` |

---

## Key Findings and Visualizations

# Useful site to select colors https://www.color-hex.com/color/4b0082

### 🟣 Correlation Heatmap
Revealed that **flavonoids** and **total_phenols** are strongly correlated (r ≈ 0.86), indicating chemical similarity.

### 🟢 Scatter Matrix
Plots of **alcohol percentage**, **color intensity**, and **proline** showed clear grouping by wine class.

### ⚪ Scatter Plot
“Alcohol vs Color Intensity” demonstrated distinct class separation, especially for Class 0 and Class 1.

### 🟣 Class Distribution
Class 1 had slightly more samples than Classes 0 or 2, but all were relatively balanced.

---

## Feature Selection
**Target Variable (y):** `wine_class`  
**Selected Features (X):**
- `alcohol_pct`  
- `color_intensity`  
- `proline`  
- `phenolic_ratio`

These features were chosen for their ability to capture **chemical composition** and **visual appearance**, both essential for wine classification.

---

## Splitting the Data
Two approaches were compared:
1. **Basic Random Split** (80/20)
2. **Stratified Split** to maintain class balance

**Result:**  
The stratified split produced nearly identical class distributions in training and test sets, preventing bias.

| Dataset | Class 1 | Class 0 | Class 2 |
|----------|----------|----------|----------|
| Original | 0.399 | 0.331 | 0.270 |
| Train    | 0.401 | 0.331 | 0.268 |
| Test     | 0.389 | 0.333 | 0.278 |

---

### Reflections

**1. What did you learn from this dataset compared to Titanic?**  
This project focused more on numbers and measurements instead of people and categories. It helped me see how chemical features like alcohol, color intensity, and proline can be just as meaningful for prediction as social features were in the Titanic dataset.  

**2. How did data quality affect your process?**  
The Wine dataset didn’t need cleaning, so I could go straight into visualization and analysis. That made it easier to focus on relationships between features instead of fixing missing data.  

**3. What did your visuals reveal?**  
Color intensity and proline stood out as the most useful predictors since they separated the wine classes really well. Seeing those differences in scatter plots made it easier to understand how classification works.  

**4. What was your overall takeaway?**  
Both projects followed the same process—inspect, clean, visualize, and split the data—but they applied it to totally different problems. That showed me how flexible data science can be across fields.

---

## Tools and Libraries
- Python  
- pandas  
- NumPy  
- seaborn  
- matplotlib  
- scikit-learn  