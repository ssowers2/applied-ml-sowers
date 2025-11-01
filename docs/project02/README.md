# 🔹Sabriya Sowers' Titanic Survival Analysis🔹

**Author:** Sabriya Sowers  
**Date:** October 30, 2025  

## Project Overview
This project analyzes the Titanic dataset (loaded from the Seaborn library) to explore which factors may have influenced passenger survival. The notebook walks through data exploration, feature engineering, and preparation for building a classification model.

## Goals
- Inspect and understand the dataset structure
- Identify missing values and basic statistics
- Visualize key relationships between features
- Engineer useful features
- Select predictor variables (X) and a target variable (y)
- Create train/test splits, including a stratified split

## Dataset
The dataset includes 891 passengers and 15 features such as:
- `survived` (0/1)
- `pclass` (passenger class)
- `sex`
- `age`
- `fare`
- `sibsp` (siblings/spouses aboard)
- `parch` (parents/children aboard)
- `embarked` (port of embarkation)
- and others

Some columns have missing values (for example, `age` and `deck`).

## Key Steps in the Notebook

### 1. Import and Inspect the Data
- Load the Titanic dataset with `sns.load_dataset("titanic")`
- View columns, data types, missing values, and summary stats
- Check correlations between numeric features

### 2. Explore and Visualize
- Scatter plots (e.g. age vs fare, colored by sex)
- Class vs survival count plots
- Age distribution histogram
- Scatter matrix for numeric features

These visuals show patterns like:
- First-class passengers survived more often
- Females survived more often than males
- Younger passengers tended to be in lower classes

### 3. Feature Engineering
New columns were created to help modeling:
- `family_size` = `sibsp + parch + 1`
- `sex` converted to numeric (male=0, female=1)
- `embarked` mapped to numeric values
- `alone` converted from boolean to 0/1

These steps prepare the data for machine learning.

### 4. Feature Selection
The model is set up to predict `survived` using:
- `age`
- `fare`
- `pclass`
- `sex`
- `family_size`

`survived` is the target (`y`).  
The other columns are the input features (`X`).

### 5. Train/Test Split
Two splitting methods are compared:
- Basic `train_test_split`
- `StratifiedShuffleSplit`, which keeps the survival rate balanced between train and test sets

Stratification is important because survival is not evenly split across the dataset (more people did not survive than survived).

---

### Reflections

**1. What did you learn from this project?**  
Working with the Titanic dataset helped me understand how data features can describe real human behavior and outcomes. It was interesting to see how class, gender, and age all connected to survival rates.  

**2. What challenges did you face?**  
Handling missing data for fields like age and deck took extra work, and learning to encode categorical features into numbers was an important step for model preparation.  

**3. What stood out most from your visuals?**  
The patterns were clear that females and first-class passengers had much higher survival rates. The scatter plots and count plots really helped highlight this.

**4. What was your biggest takeaway?**  
The project showed how feature selection and data cleaning directly affect model accuracy. It also made me more comfortable using libraries like pandas, seaborn, and scikit-learn to prepare real-world data for analysis.

---

## Tools and Libraries
- Python
- pandas
- NumPy
- seaborn
- matplotlib
- scikit-learn