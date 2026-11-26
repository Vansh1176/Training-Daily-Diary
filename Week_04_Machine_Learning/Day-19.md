# Day 19 – Model Training and Testing

**Date:** __________

## Aim
To understand the difference between training and testing data and implement a basic Machine Learning model.

## Introduction
Model training is the process in which an algorithm learns patterns from training data. Testing is performed on separate data that the model did not use during training. This helps estimate how well the model may perform on unseen examples.

## Training and Testing
- **Training set:** Used to fit the model.
- **Testing set:** Used to evaluate the trained model.
- **Features (X):** Input variables.
- **Target (y):** The value or class that the model learns to predict.

A common split is 80% for training and 20% for testing, but the correct ratio depends on dataset size and project requirements.

## Practical: Train a Classification Model

This example uses the built-in Iris dataset and a Decision Tree classifier.

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Divide data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

print("Training records:", len(X_train))
print("Testing records:", len(X_test))

# Create and train the model
model = DecisionTreeClassifier(random_state=42)
model.fit(X_train, y_train)

# Predict the test data
y_pred = model.predict(X_test)

print("Predictions:", y_pred[:10])
print("Actual values:", y_test[:10])
print("Accuracy:", accuracy_score(y_test, y_pred))
```

## Making a Prediction for New Data

```python
# One new flower record:
# sepal length, sepal width, petal length, petal width
new_flower = [[5.1, 3.5, 1.4, 0.2]]

predicted_class = model.predict(new_flower)
print("Predicted class:", iris.target_names[predicted_class[0]])
```

The input values must use the same feature order and units as the training dataset.

## Why Should We Keep Test Data Separate?
If the model is evaluated on the same records used for training, the evaluation may give an overly optimistic result. A separate test set provides a more realistic check of generalisation.

## Learning Outcomes
- Understood the role of training and testing datasets.
- Applied `train_test_split()`.
- Trained a Decision Tree classification model.
- Generated predictions for test records and a new input.

## Conclusion
Today I learned how to divide a dataset into training and testing parts, train a classification model, and use the model to predict the class of new data.
