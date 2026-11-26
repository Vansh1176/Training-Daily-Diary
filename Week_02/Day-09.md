# Day 09 – Outlier Detection and Treatment

## 1. Objective

To understand outliers, identify unusual observations in numerical data, and learn common detection and treatment methods using Python.

## 2. Introduction

An outlier is a data point that is unusually far from the other observations in a dataset. Outliers may occur due to data-entry mistakes, measurement errors, or genuine unusual events.

Outliers should be investigated before being removed because they may contain important information.

## 3. Topics Covered

### 3.1 What Is an Outlier?

Consider the marks:

`45, 48, 50, 52, 49, 51, 150`

The value `150` is unusually high compared with the other observations and may be an outlier.

### 3.2 Common Methods of Outlier Detection

- Interquartile Range (IQR) method
- Z-score method
- Box plot
- Scatter plot

### 3.3 Interquartile Range (IQR) Method

The IQR is the difference between the third quartile (Q3) and first quartile (Q1).

**Formula:**

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 * IQR
Upper Bound = Q3 + 1.5 * IQR
```

Values below the lower bound or above the upper bound are flagged as potential outliers.

## 4. Practical Implementation

### 4.1 Create a Dataset

```python
import pandas as pd

data = {
    "Marks": [45, 48, 50, 52, 49, 51, 150, 47, 53, 46]
}

df = pd.DataFrame(data)
print(df)
```

### 4.2 Calculate Quartiles and IQR

```python
Q1 = df["Marks"].quantile(0.25)
Q3 = df["Marks"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

print("Q1:", Q1)
print("Q3:", Q3)
print("IQR:", IQR)
print("Lower Bound:", lower_bound)
print("Upper Bound:", upper_bound)
```

### 4.3 Identify Outliers

```python
outliers = df[
    (df["Marks"] < lower_bound) |
    (df["Marks"] > upper_bound)
]

print("Potential Outliers:")
print(outliers)
```

### 4.4 Filter Potential Outliers

```python
filtered_df = df[
    (df["Marks"] >= lower_bound) &
    (df["Marks"] <= upper_bound)
]

print(filtered_df)
```

Filtering is only one possible treatment. First investigate whether the unusual value is an error or a genuine observation.

### 4.5 Visualize Outliers Using a Box Plot

```python
import matplotlib.pyplot as plt

plt.boxplot(df["Marks"])
plt.title("Box Plot of Student Marks")
plt.ylabel("Marks")
plt.show()
```

### 4.6 Detect Outliers Using Z-Score

```python
from scipy.stats import zscore

df["Z_Score"] = zscore(df["Marks"])

print(df)

outliers_z = df[df["Z_Score"].abs() > 3]
print("\nPotential Outliers using Z-score:")
print(outliers_z)
```

A common rule flags absolute Z-scores greater than 3. This rule is most useful when the distribution is reasonably close to normal.

## 5. Common Outlier Treatment Methods

1. **Removal:** Remove a value only when it is confirmed to be invalid or when removal is justified.
2. **Capping:** Replace extreme values with selected lower and upper limits.
3. **Transformation:** Apply transformations such as logarithms when appropriate.
4. **Retention:** Keep genuine unusual observations if they are meaningful.

### Example of Capping

```python
capped_df = df.copy()

capped_df["Marks_Capped"] = df["Marks"].clip(
    lower=lower_bound,
    upper=upper_bound
)

print(capped_df)
```

## 6. Learning Outcomes

- Understood the meaning and causes of outliers.
- Learned the IQR method.
- Practiced calculating quartiles and boundaries.
- Identified potential outliers using Python.
- Visualized numerical data using a box plot.
- Explored Z-score and capping techniques.

## 7. Conclusion

On Day 9, I learned how to detect and investigate outliers using IQR, Z-score, and box plots. I also explored different treatment methods and understood why unusual values should not be removed without proper investigation.
