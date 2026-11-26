# Day 13 – Statistical Distribution and Correlation Analysis

## 1. Objective

To understand basic statistical measures, examine numerical data distributions, and study relationships between variables using correlation.

## 2. Introduction

Statistical analysis helps summarize and interpret data. Measures such as mean, median, mode, variance, and standard deviation describe the center and spread of numerical observations.

Correlation measures the direction and strength of association between two numerical variables.

## 3. Topics Covered

### 3.1 Mean

The mean is the average of all observations.

```python
import pandas as pd

marks = pd.Series([60, 70, 80, 90, 100])
print("Mean:", marks.mean())
```

### 3.2 Median

The median is the middle value after arranging observations in order.

```python
print("Median:", marks.median())
```

### 3.3 Mode

The mode is the most frequently occurring value.

```python
values = pd.Series([60, 70, 70, 80, 90])
print("Mode:", values.mode().tolist())
```

### 3.4 Variance and Standard Deviation

Variance measures how spread out observations are from the mean. Standard deviation is the square root of variance.

```python
print("Variance:", marks.var())
print("Standard Deviation:", marks.std())
```

## 4. Practical Dataset

```python
import pandas as pd

data = {
    "Study_Hours": [1, 2, 3, 4, 5, 6],
    "Marks": [50, 55, 65, 70, 85, 90],
    "Attendance": [60, 65, 70, 75, 90, 95]
}

df = pd.DataFrame(data)
print(df)
```

## 5. Distribution Visualization

### 5.1 Histogram

```python
import matplotlib.pyplot as plt

plt.hist(df["Marks"], bins=5, edgecolor="black")
plt.title("Distribution of Student Marks")
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.show()
```

### 5.2 Density Plot

```python
import seaborn as sns

sns.kdeplot(data=df, x="Marks", fill=True)
plt.title("Marks Density Distribution")
plt.show()
```

### 5.3 Box Plot

```python
sns.boxplot(data=df, y="Marks")
plt.title("Box Plot of Marks")
plt.show()
```

## 6. Correlation Analysis

Correlation values range from -1 to +1.

- **Positive correlation:** Variables tend to increase together.
- **Negative correlation:** One variable tends to decrease as the other increases.
- **Near-zero correlation:** Little or no linear association is observed.

```python
correlation = df.corr(numeric_only=True)
print(correlation)
```

### 6.1 Correlation Heatmap

```python
sns.heatmap(
    correlation,
    annot=True,
    cmap="coolwarm",
    fmt=".2f"
)

plt.title("Correlation Heatmap")
plt.show()
```

### 6.2 Scatter Plot

```python
plt.scatter(df["Study_Hours"], df["Marks"])
plt.title("Study Hours vs Marks")
plt.xlabel("Study Hours")
plt.ylabel("Marks")
plt.show()
```

Correlation does not establish causation. Other factors may influence the observed relationship.

## 7. Learning Outcomes

- Learned mean, median, mode, variance, and standard deviation.
- Visualized distributions using histograms, density plots, and box plots.
- Calculated correlation between numerical variables.
- Created a correlation heatmap.
- Understood positive, negative, and weak linear relationships.

## 8. Conclusion

On Day 13, I learned how statistical measures describe data and how visualizations help understand numerical distributions. I also practiced correlation analysis to examine relationships between variables.
