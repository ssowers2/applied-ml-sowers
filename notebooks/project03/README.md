# Titanic Survival Analysis

**Author:** Sabriya Sowers  
**Date:** November 6, 2025

## Classifiers Used in This Project

In this project, we use the Titanic dataset to build and evaluate three different classification models. Each model approaches prediction in a different way, which helps us compare how model structure and complexity affect performance.

### 1. Decision Tree Classifier (DT)
A **Decision Tree** works like a flowchart. It repeatedly asks questions about the data and splits into branches until reaching a final classification.

**Strengths:** Easy to interpret and visualize.  
**Limitations:** Can **overfit** if the tree becomes too deep.

### 2. Support Vector Machine (SVM)
A **Support Vector Machine** finds the best boundary (hyperplane) to separate classes. It relies on key data points called **support vectors**.

**Strengths:** Effective in complex separation problems.  
**Limitations:** Requires tuning and can be slower on large datasets.

### 3. Neural Network (NN)
A **Neural Network** uses connected layers of “neurons” to learn patterns, including non-linear relationships.

**Strengths:** Very flexible and powerful with complex data.  
**Limitations:** Harder to interpret and may require more tuning.

---

### Why Use Multiple Models?
Using multiple classifiers helps compare:
- **How well different approaches learn from the data**
- Which **features** are more predictive
- Which models **generalize** better to unseen data

In this project:
- Decision Trees show **feature-based splits**
- SVM identifies **boundary margins**
- Neural Network captures **subtle patterns**

---

## Key Steps in the Project

1. **Loaded and cleaned the Titanic dataset**  
   - Filled missing ages using the median  
   - Filled missing embarkation towns using the mode  

2. **Engineered new feature: `family_size`**  
   - Calculated from number of siblings/spouses + parents/children + the passenger  

3. **Converted categorical data to numeric**  
   - `sex` → male = 0, female = 1  
   - `embarked` → C = 0, Q = 1, S = 2  
   - `alone` → True = 1, False = 0  

4. **Created three feature cases**
   - **Case 1:** `alone`
   - **Case 2:** `age`
   - **Case 3:** `age` + `family_size`

5. **Trained and evaluated models**
   - Decision Tree → All three cases
   - SVM → All three cases (RBF Kernel)
   - Neural Network → Case 3 only

---

## Final Thoughts & Insights
| Model Type           | Case   | Features Used         | Accuracy | Precision | Recall | F1-Score | Notes |
|----------------------|--------|-----------------------|----------|-----------|--------|----------|-------|
| Decision Tree        | Case 1 | alone                 | 63%      | 64%       | 63%    | 63%      | Performs similarly to SVM; simple split on alone is limited. |
| Decision Tree        | Case 2 | age                   | 61%      | 58%       | 61%    | 55%      | Age alone did not predict survival well (especially survivors). |
| Decision Tree        | Case 3 | age + family_size     | 59%      | 57%       | 59%    | 58%      | Slight overfitting, training was higher than test accuracy. |
| SVM (RBF Kernel)     | Case 1 | alone                 | 63%      | 64%       | 63%    | 63%      | Single feature gives limited separation. |
| SVM (RBF Kernel)     | Case 2 | age                   | 63%      | 66%       | 63%    | 52%      | Improved precision but low recall for survivors. |
| SVM (RBF Kernel)     | Case 3 | age + family_size     | 63%      | 66%       | 63%    | 52%      | Extra feature didn’t noticeably improve performance. |
| Neural Network (MLP) | Case 3 | age + family_size     | 66%      | 65%       | 66%    | 65%      | Best performance overall, captured more complex patterns. |

## Challenges Faced
One challenge in this project was identifying features that made a meaningful impact on survival. Some features, such as `age` or `alone`, did not strongly predict survival on their own, which led to lower recall (especially for survivors). Another challenge was avoiding overfitting, particularly with the Decision Tree in Case 3 where training accuracy was higher than test accuracy. This showed the importance of testing models on unseen data to check generalization.

---

## Next Steps
To improve performance, the next step would be to include additional features such as passenger class (`pclass`), fare, or gender (`sex`), which research shows are more strongly linked to survival. I could also experiment with parameter tuning, such as adjusting SVM kernel settings or changing the number of hidden units in the Neural Network. This may help increase accuracy and create clearer decision boundaries.

- The **Neural Network performed best**, but only slightly better than SVM.  
- **Age alone** was not a strong predictor.  
- Adding **family_size** did not dramatically improve performance for SVM, suggesting other features (like class, fare, or gender) may contribute more.
- The strongest takeaway is that **feature selection matters** as much as the algorithm itself.

---

## Tools and Libraries
- Python
- pandas
- NumPy
- seaborn
- matplotlib
- scikit-learn