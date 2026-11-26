# Day 17 – Types of Machine Learning

**Date:** __________

## Aim
To study the major types of Machine Learning and understand their use cases.

## Introduction
Machine Learning approaches are commonly grouped into supervised learning, unsupervised learning, and reinforcement learning. The suitable approach depends on the problem and the available data.

## 1. Supervised Learning
In supervised learning, the model is trained using labelled data. Each training example contains input features and the correct target value.

Common tasks:
- **Regression:** Predicts a numerical value, such as house price or delivery time.
- **Classification:** Predicts a category, such as spam/not spam or approved/rejected.

Examples of algorithms include Linear Regression, Decision Tree, K-Nearest Neighbours, and Logistic Regression.

## 2. Unsupervised Learning
In unsupervised learning, the data does not contain a target label. The algorithm tries to discover patterns or groups in the data.

A common task is **clustering**, where similar records are grouped together. K-Means is one popular clustering algorithm.

## 3. Reinforcement Learning
In reinforcement learning, an agent learns by interacting with an environment. It receives rewards or penalties and tries to improve its actions over time.

Examples include game-playing agents and robot navigation.

## Practical 1: Supervised Learning – Classification

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

# Load a labelled flower dataset
iris = load_iris()
X = iris.data
y = iris.target

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

model = DecisionTreeClassifier(random_state=42)
model.fit(X_train, y_train)

predictions = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, predictions))
```

## Practical 2: Unsupervised Learning – K-Means Clustering

```python
from sklearn.datasets import load_iris
from sklearn.cluster import KMeans

iris = load_iris()
X = iris.data

kmeans = KMeans(n_clusters=3, random_state=42, n_init=10)
clusters = kmeans.fit_predict(X)

print("First 10 cluster labels:", clusters[:10])
print("Cluster centres:")
print(kmeans.cluster_centers_)
```

**Observation:** The cluster labels are group identifiers created by the algorithm. They are not the original flower class labels and their numeric order has no special meaning.

## Comparison

| Type | Training data | Main purpose |
|---|---|---|
| Supervised | Labelled | Predict a known target |
| Unsupervised | Unlabelled | Discover hidden patterns |
| Reinforcement | Feedback from environment | Learn actions through rewards |

## Learning Outcomes
- Understood supervised, unsupervised, and reinforcement learning.
- Differentiated regression and classification.
- Practised a classification model and a clustering algorithm.

## Conclusion
Today I learned the major types of Machine Learning and their applications. I also implemented Decision Tree classification and K-Means clustering using Scikit-learn.
