# Day 18 – Data Preprocessing and Feature Selection

**Date:** __________

## Aim
To understand why data preprocessing is required and learn basic techniques for preparing data before model training.

## Introduction
Real-world datasets may contain missing values, duplicate records, inconsistent categories, and features with different scales. Data preprocessing helps convert raw data into a suitable form for Machine Learning.

## Common Preprocessing Steps

1. **Handling missing values:** Fill missing values or remove records when appropriate.
2. **Removing duplicates:** Identify repeated records and decide whether they should be removed.
3. **Encoding categorical data:** Convert text categories into numeric representations.
4. **Feature scaling:** Bring numerical features to comparable scales.
5. **Feature selection:** Keep useful input columns and remove irrelevant or redundant ones.
6. **Train-test split:** Keep a separate portion of data for evaluating the model.

## Practical: Preprocessing with Scikit-learn

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder, StandardScaler
from sklearn.impute import SimpleImputer
from sklearn.pipeline import Pipeline

# Small example dataset
df = pd.DataFrame({
    "age": [20, 25, None, 32, 28, 40],
    "city": ["Delhi", "Pune", "Delhi", None, "Mumbai", "Pune"],
    "income": [25000, 40000, 30000, 52000, None, 65000],
    "purchased": [0, 1, 0, 1, 1, 1]
})

X = df.drop(columns="purchased")
y = df["purchased"]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.33, random_state=42, stratify=y
)

numeric_features = ["age", "income"]
categorical_features = ["city"]

numeric_pipeline = Pipeline(steps=[
    ("imputer", SimpleImputer(strategy="median")),
    ("scaler", StandardScaler())
])

categorical_pipeline = Pipeline(steps=[
    ("imputer", SimpleImputer(strategy="most_frequent")),
    ("encoder", OneHotEncoder(handle_unknown="ignore"))
])

preprocessor = ColumnTransformer(transformers=[
    ("numeric", numeric_pipeline, numeric_features),
    ("categorical", categorical_pipeline, categorical_features)
])

X_train_ready = preprocessor.fit_transform(X_train)
X_test_ready = preprocessor.transform(X_test)

print("Training data shape:", X_train_ready.shape)
print("Testing data shape:", X_test_ready.shape)
```

**Important:** Fit preprocessing steps only on the training data. Then use the fitted transformations on the test data. This helps prevent data leakage.

## Feature Selection
Feature selection means choosing the input columns that are useful for predicting the target.

Possible methods:
- Domain knowledge
- Correlation analysis
- Statistical tests
- Model-based feature importance

Do not select features using information from the test target. The test set should remain separate until final evaluation.

## Learning Outcomes
- Understood the need for data preprocessing.
- Practised imputing missing values.
- Learned categorical encoding and numerical scaling.
- Understood train-test splitting and data leakage.
- Learned the purpose of feature selection.

## Conclusion
Today I learned how to prepare raw data for Machine Learning. I implemented missing-value handling, one-hot encoding, feature scaling, and a preprocessing pipeline using Scikit-learn.
