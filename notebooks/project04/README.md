

## Understanding `train_test_split`
The following lines:
```python
X1_train, X1_test, y1_train, y1_test = train_test_split(X1, y1, test_size=0.2, random_state=123)
X2_train, X2_test, y2_train, y2_test = train_test_split(X2, y2, test_size=0.2, random_state=123)
X3_train, X3_test, y3_train, y3_test = train_test_split(X3, y3, test_size=0.2, random_state=123)
X4_train, X4_test, y4_train, y4_test = train_test_split(X4, y4, test_size=0.2, random_state=123)

all perform the same task:
They split the dataset into a training set and a test set for each case.

What the split does
Each call to train_test_split separates your inputs (X) and target (y) into:
Training data (80%) → used to fit the model
Testing data (20%) → used to evaluate performance on unseen data
This lets you check how well the model generalizes, not just how well it memorizes.

Parameters explained
test_size=0.2
20% of the data goes into the test set
80% goes into the training set
random_state=123
Ensures the split is the same every time you run the notebook
Makes results consistent and reproducible

Why splitting is important
Using separate training and testing sets prevents overfitting.
The model learns patterns from the training data, then we evaluate it using the test data, which simulates real-world prediction on unseen examples.

What each case represents
Each split corresponds to a different feature set:
Case 1: age
Case 2: family_size
Case 3: age and family_size
Case 4: selected features (e.g., pclass, age, family_size)

### Setup virtual environment
1. uv venv
2. uv python pin 3.12
3. uv sync --extra dev --extra docs --upgrade
4. .\.venv\Scripts\Activate
5. uv add --dev pre-commit ruff
6. uv run python --version