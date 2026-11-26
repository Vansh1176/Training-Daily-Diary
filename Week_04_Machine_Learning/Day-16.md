# Day 16 – Introduction to Machine Learning

**Date:** __________

## Aim
To understand the meaning, importance, types, and basic workflow of Machine Learning.

## Introduction
Machine Learning (ML) is a branch of Artificial Intelligence that allows computers to learn patterns from data and make predictions or decisions without being explicitly programmed for every situation.

For example, an email service can learn from previously labelled emails and identify whether a new email is spam or not.

## AI, ML and Deep Learning
- **Artificial Intelligence (AI):** A broad field focused on making machines perform tasks that normally require human intelligence.
- **Machine Learning (ML):** A part of AI in which systems learn patterns from data.
- **Deep Learning (DL):** A part of ML that uses neural networks with multiple layers.

## Basic Machine Learning Workflow
1. Define the problem.
2. Collect the required data.
3. Explore and clean the data.
4. Prepare features and target values.
5. Split data into training and testing sets.
6. Select and train a model.
7. Evaluate the model.
8. Use the model to make predictions.

## Practical: A Simple Prediction Example

The following example creates a small dataset and trains a Linear Regression model to predict marks based on study hours.

```python
import pandas as pd
from sklearn.linear_model import LinearRegression

# Sample dataset
data = {
    "Study_Hours": [1, 2, 3, 4, 5, 6],
    "Marks": [35, 40, 50, 55, 65, 70]
}

df = pd.DataFrame(data)
print(df)

# Feature and target
X = df[["Study_Hours"]]
y = df["Marks"]

# Train the model
model = LinearRegression()
model.fit(X, y)

# Predict marks for 7 study hours
prediction = model.predict([[7]])
print("Predicted marks:", round(prediction[0], 2))
```

**Note:** This is a small demonstration dataset created for learning. Its prediction is illustrative and is not a guarantee of real examination performance.

## Important Terms
- **Feature:** An input column used by the model, such as study hours.
- **Target:** The value to be predicted, such as marks.
- **Model:** The learned mathematical pattern used to make predictions.
- **Training:** The process of teaching a model using data.
- **Prediction:** The output produced by a trained model for new input.

## Learning Outcomes
- Understood the meaning of Machine Learning.
- Learned the relationship between AI, ML, and Deep Learning.
- Understood the main steps of an ML workflow.
- Built a simple Linear Regression model.

## Conclusion
Today I learned the basic concepts of Machine Learning and understood how a model learns from data to make predictions. I also implemented a simple Linear Regression example using Python and Scikit-learn.
