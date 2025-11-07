# Titanic Survival Analysis

**Author:** Sabriya Sowers  
**Date:** October 30, 2025  

## Classifiers Used in This Project

In this project, we use the Titanic dataset to build and evaluate three different classification models. Each model approaches prediction in a different way, which helps us compare how model structure and complexity affect performance.

### 1. Decision Tree Classifier (DT)
A **Decision Tree** works like a flowchart. It repeatedly asks questions about the data (for example, “Was the passenger alone?”) and splits the dataset into branches based on the answers. This continues until the model reaches a final classification (survived or not survived).

**Strengths:**
- Very easy to **interpret** and visualize
- Fast to train

**Limitations:**
- Can **overfit** if the tree becomes too deep or complex

### 2. Support Vector Machine (SVM)
A **Support Vector Machine** tries to draw the **best possible boundary** between classes. This boundary is called a **hyperplane**. The model focuses on the data points nearest to the dividing line, known as **support vectors**, which determine the margin between the classes.

**Strengths:**
- Works well when there is a clear separation between classes
- Effective on smaller datasets with complex boundaries

**Limitations:**
- Can be **computationally expensive** on large datasets
- May require tuning kernel types for the best fit

### 3. Neural Network (NN)
A **Neural Network** is inspired by how the human brain processes information. It uses **layers of neurons** that learn relationships in the data. The network adjusts its internal weights based on errors, improving predictions over time.

**Strengths:**
- Handles **complex**, non-linear patterns
- Very flexible and powerful with the right tuning

**Limitations:**
- Requires **more data** and careful parameter tuning
- Harder to interpret than Decision Trees

---

### Why Use Multiple Models?
Using more than one classifier allows us to:
- Understand how **different learning approaches** impact performance
- Identify which **features and patterns** matter most
- Compare strengths and weaknesses of **simple vs. complex** models

In this project:
- **Decision Trees** show how individual features contribute to the outcome
- **SVMs** help identify more **precise decision boundaries**
- **Neural Networks** capture **subtle and non-linear** relationships

## Key Steps in Project

## Tools and Libraries
- Python
- pandas
- NumPy
- seaborn
- matplotlib
- scikit-learn