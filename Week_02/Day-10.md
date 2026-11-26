# Day 10 – Exploratory Data Analysis (EDA)

## 1. Objective

To understand Exploratory Data Analysis (EDA) and learn how to summarize, visualize, and explore datasets to identify patterns, trends, and relationships.

## 2. Introduction

Exploratory Data Analysis is the process of examining a dataset using statistical summaries and visualizations. It helps understand the data before applying machine learning algorithms or making decisions.

EDA can reveal missing values, unusual observations, distributions, and relationships between variables.

## 3. Types of EDA

### 3.1 Univariate Analysis

Univariate analysis examines one variable at a time.

Examples:
- Distribution of student marks
- Count of students in each city
- Average age

### 3.2 Bivariate Analysis

Bivariate analysis examines the relationship between two variables.

Examples:
- Age versus marks
- Study hours versus marks
- City versus average marks

### 3.3 Multivariate Analysis

Multivariate analysis examines three or more variables together to understand more complex relationships.

## 4. Practical Dataset

```python
import pandas as pd
import numpy as np

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Karan", "Neha"],
    "Age": [20, 21, 19, 22, 20, 21],
    "Study_Hours": [2, 5, 3, 6, 1, 4],
    "Marks": [65, 90, 70, 95, 55, 85],
    "City": ["Delhi", "Mumbai", "Delhi", "Pune", "Mumbai", "Pune"]
}

df = pd.DataFrame(data)
print(df)
```

## 5. Basic EDA

```python
print(df.head())
print(df.info())
print(df.describe())
print(df.isnull().sum())
```

## 6. Univariate Analysis

### 6.1 Histogram

A histogram shows the distribution of a numerical variable.

```python
import matplotlib.pyplot as plt

plt.hist(df["Marks"], bins=5, edgecolor="black")
plt.title("Distribution of Student Marks")
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.show()
```

### 6.2 Bar Chart

A bar chart compares values across categories.

```python
df["City"].value_counts().plot(kind="bar")
plt.title("Number of Students by City")
plt.xlabel("City")
plt.ylabel("Number of Students")
plt.show()
```

### 6.3 Box Plot

A box plot summarizes the spread of numerical data and helps identify potential outliers.

```python
plt.boxplot(df["Marks"])
plt.title("Marks Box Plot")
plt.ylabel("Marks")
plt.show()
```

## 7. Bivariate Analysis

### 7.1 Scatter Plot

A scatter plot helps examine the relationship between two numerical variables.

```python
plt.scatter(df["Study_Hours"], df["Marks"])
plt.title("Study Hours vs Marks")
plt.xlabel("Study Hours")
plt.ylabel("Marks")
plt.show()
```

### 7.2 Grouped Average

```python
city_marks = df.groupby("City")["Marks"].mean()

print(city_marks)

city_marks.plot(kind="bar")
plt.title("Average Marks by City")
plt.xlabel("City")
plt.ylabel("Average Marks")
plt.show()
```

## 8. Multivariate Analysis

### 8.1 Correlation Matrix

Correlation measures the strength and direction of a linear relationship between numerical variables.

```python
correlation = df[["Age", "Study_Hours", "Marks"]].corr()

print(correlation)
```

### 8.2 Correlation Heatmap

```python
import seaborn as sns

sns.heatmap(
    correlation,
    annot=True,
    cmap="coolwarm",
    fmt=".2f"
)

plt.title("Correlation Heatmap")
plt.show()
```

Correlation does not prove that one variable causes another.

## 9. Crosstab Analysis

A crosstab displays the frequency distribution of two categorical variables.

```python
table = pd.crosstab(df["City"], df["Name"])

print(table)
```

A more useful example using a derived category:

```python
df["Performance"] = df["Marks"].apply(
    lambda x: "High" if x >= 80 else "Average"
)

result = pd.crosstab(df["City"], df["Performance"])

print(result)
```

## 10. Feature Engineering – Basic Example

Feature engineering means creating or transforming variables to make them more useful for analysis or machine learning.

```python
df["Marks_Category"] = df["Marks"].apply(
    lambda x: "Excellent" if x >= 90
    else "Good" if x >= 75
    else "Needs Improvement"
)

print(df[["Name", "Marks", "Marks_Category"]])
```

## 11. Learning Outcomes

- Understood the purpose of Exploratory Data Analysis.
- Differentiated between univariate, bivariate, and multivariate analysis.
- Created histograms, bar charts, box plots, and scatter plots.
- Calculated correlation between numerical variables.
- Created a correlation heatmap.
- Practiced crosstab and basic feature engineering.

## 12. Conclusion

On Day 10, I learned how to explore datasets using statistical summaries and visualizations. I practiced univariate, bivariate, and multivariate analysis, along with correlation, crosstab, and basic feature engineering. EDA helps understand data and identify useful patterns before further analysis or model development.
