# Day 20 – Model Evaluation and Prediction

**Date:** __________

## Aim
To learn common model evaluation metrics and understand how to save and reuse a trained Machine Learning model.

## Introduction
After training a model, its performance must be evaluated using suitable metrics. The choice of metric depends on the problem. Classification and regression use different evaluation measures.

## Classification Metrics
- **Accuracy:** Fraction of all predictions that are correct.
- **Precision:** Of the records predicted as positive, how many are actually positive?
- **Recall:** Of all actual positive records, how many were identified?
- **F1-score:** Harmonic mean of precision and recall.
- **Confusion matrix:** Table showing correct and incorrect class predictions.

Accuracy alone may be misleading when classes are imbalanced. Precision, recall, and F1-score can provide additional information.

## Regression Metrics
- **MAE:** Mean Absolute Error; average absolute difference between actual and predicted values.
- **MSE:** Mean Squared Error; average squared prediction error.
- **RMSE:** Square root of MSE, expressed in the target's units.
- **R² score:** Indicates how much variation in the target is explained by the model, relative to a baseline.

## Practical: Evaluate a Classification Model

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import (
    accuracy_score, classification_report, confusion_matrix
)

iris = load_iris()
X = iris.data
y = iris.target

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

model = DecisionTreeClassifier(random_state=42)
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("\\nClassification Report:")
print(classification_report(y_test, y_pred, target_names=iris.target_names))
print("Confusion Matrix:")
print(confusion_matrix(y_test, y_pred))
```

## Practical: Save and Load the Model

```python
import joblib

# Save the trained model
joblib.dump(model, "iris_model.pkl")

# Load the saved model
loaded_model = joblib.load("iris_model.pkl")

# Make a prediction using the loaded model
sample = [[5.1, 3.5, 1.4, 0.2]]
prediction = loaded_model.predict(sample)

print("Predicted flower:", iris.target_names[prediction[0]])
```

The saved model file should be kept with information about the dataset, feature order, preprocessing steps, and software versions. Never load a model file from an untrusted source.

## End-to-End ML Workflow Recap
1. Understand the problem.
2. Collect and inspect data.
3. Clean and preprocess data.
4. Select useful features.
5. Split the data.
6. Train the model.
7. Evaluate performance.
8. Make predictions.
9. Save and document the model.

## Learning Outcomes
- Learned common classification and regression metrics.
- Evaluated a classification model using accuracy, a classification report, and a confusion matrix.
- Generated predictions using a trained model.
- Saved and loaded a model using Joblib.

## Conclusion
Today I learned how to evaluate Machine Learning models and why different metrics are needed for different tasks. I also practised saving and loading a trained model and completed a basic end-to-end ML workflow.

## Final Week Reflection
During this week, I studied the fundamentals and types of Machine Learning, data preprocessing, model training, testing, evaluation, and prediction. These concepts provide a foundation for building larger projects using real-world datasets.
