# Day 08 – Handling Missing Values and Duplicate Records

## 1. Objective

To identify missing values and duplicate records in a dataset and learn suitable techniques to handle them using Pandas.

## 2. Introduction

Real-world datasets are not always complete or consistent. Some records may contain blank values, while others may be repeated. These problems can affect analysis and model performance.

Data cleaning is the process of identifying and correcting such quality issues.

## 3. Topics Covered

### 3.1 Missing Values

Missing values are entries for which information is unavailable. In Pandas, missing values are commonly represented by `NaN` or `None`.

### 3.2 Detecting Missing Values

```python
import pandas as pd
import numpy as np

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Karan"],
    "Age": [20, np.nan, 19, 22, np.nan],
    "Marks": [78, 92, np.nan, 88, 74],
    "City": ["Delhi", "Mumbai", "Delhi", None, "Pune"]
}

df = pd.DataFrame(data)

print(df.isnull())
print("\nMissing values in each column:")
print(df.isnull().sum())
```

### 3.3 Calculating Missing Value Percentage

```python
missing_percentage = (df.isnull().sum() / len(df)) * 100
print(missing_percentage)
```

### 3.4 Removing Missing Values

`dropna()` removes rows or columns containing missing values.

```python
clean_df = df.dropna()
print(clean_df)
```

Use removal only when it is appropriate; deleting too many records can cause information loss.

### 3.5 Filling Missing Values

**Fill numerical columns with the mean:**

```python
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["Marks"] = df["Marks"].fillna(df["Marks"].median())
```

**Fill categorical columns with the mode:**

```python
df["City"] = df["City"].fillna(df["City"].mode()[0])
```

The mean is sensitive to extreme values, so the median may be more suitable for skewed numerical data.

### 3.6 Duplicate Records

Duplicate records are repeated rows or entries in a dataset.

Detect duplicates:

```python
print("Duplicate rows:", df.duplicated().sum())
```

Remove duplicates:

```python
df = df.drop_duplicates()
```

Check duplicates using selected columns:

```python
print(df.duplicated(subset=["Name"]).sum())
```

## 4. Complete Practical Program

```python
import pandas as pd
import numpy as np

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Aman"],
    "Age": [20, np.nan, 19, 22, 20],
    "Marks": [78, 92, np.nan, 88, 78],
    "City": ["Delhi", "Mumbai", "Delhi", None, "Delhi"]
}

df = pd.DataFrame(data)

print("Original Dataset:")
print(df)

print("\nMissing Values:")
print(df.isnull().sum())

# Fill numerical missing values
df["Age"] = df["Age"].fillna(df["Age"].median())
df["Marks"] = df["Marks"].fillna(df["Marks"].median())

# Fill categorical missing values
df["City"] = df["City"].fillna(df["City"].mode()[0])

# Remove duplicate rows
df = df.drop_duplicates()

print("\nCleaned Dataset:")
print(df)

print("\nMissing Values After Cleaning:")
print(df.isnull().sum())

print("\nDuplicate Rows After Cleaning:")
print(df.duplicated().sum())
```

## 5. Best Practices

- Check missing values before selecting a treatment.
- Choose mean, median, or mode according to the data.
- Avoid removing large numbers of rows without checking the impact.
- Identify duplicates using suitable columns.
- Verify the dataset again after cleaning.

## 6. Learning Outcomes

- Understood missing values and duplicate records.
- Learned to detect missing values using `isnull()`.
- Practiced `dropna()` and `fillna()`.
- Learned to calculate missing value percentages.
- Practiced detecting and removing duplicates.

## 7. Conclusion

On Day 8, I learned how to identify and handle missing values and duplicate records in a dataset using Pandas. These cleaning techniques help improve data quality and prepare datasets for further analysis.
