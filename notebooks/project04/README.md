# README

## Understanding train_test_split

The project uses train_test_split in four places, one for each feature case:

X1_train, X1_test, y1_train, y1_test = train_test_split(X1, y1, test_size=0.2, random_state=123)
X2_train, X2_test, y2_train, y2_test = train_test_split(X2, y2, test_size=0.2, random_state=123)
X3_train, X3_test, y3_train, y3_test = train_test_split(X3, y3, test_size=0.2, random_state=123)
X4_train, X4_test, y4_train, y4_test = train_test_split(X4, y4, test_size=0.2, random_state=123)

Each line splits the data into:
- Training data (80%) – used to fit the model
- Testing data (20%) – used to evaluate the model on unseen examples

Why this matters:
Splitting the data helps prevent overfitting and lets you test how well the model generalizes.

Parameter meanings:
- test_size=0.2 → 20% test, 80% train
- random_state=123 → ensures the split is the same every time (reproducible results)

What each case represents:
Case 1: age  
Case 2: family_size  
Case 3: age + family_size  
Case 4: pclass, age, family_size

------------------------------------------------------------

## Virtual Environment Setup (uv)

1. uv venv  
2. uv python pin 3.12  
3. uv sync --extra dev --extra docs --upgrade  
4. .\.venv\Scripts\Activate  
5. uv add --dev pre-commit ruff  
6. uv run python --version  

These steps:
- Create a virtual environment
- Pin Python version to 3.12
- Install dependencies
- Set up pre-commit and ruff
- Confirm your Python version

------------------------------------------------------------

## Choosing Regression Models
Regularization helps prevent overfitting. It adds a penalty to very large coefficients so the model stays simple and generalizes better.

General guidance:
- Use Ridge if basic linear regression is overfitting.
- Use Lasso if you want the model to help select important features.
- Use Elastic Net if you want a mix of Ridge and Lasso behavior.

These options help control model complexity without needing to change the dataset.