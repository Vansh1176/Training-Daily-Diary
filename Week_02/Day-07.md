# Day 07 – Dataset Inspection Using Pandas

## 1. Objective

To learn how to load a dataset and inspect its structure, columns, data types, dimensions, and statistical summary using Pandas.

## 2. Introduction

Before cleaning or analyzing a dataset, it is important to understand its structure. Dataset inspection helps identify incorrect data types, unusual values, missing information, and other quality issues.

Pandas provides useful functions such as `head()`, `tail()`, `info()`, `describe()`, and `shape` for this purpose.

## 3. Topics Covered

### 3.1 Importing Pandas and Loading Data

```python
import pandas as pd

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Karan"],
    "Age": [20, 21, 19, 22, 20],
    "Marks": [78, 92, 65, 88, 74],
    "City": ["Delhi", "Mumbai", "Delhi", "Pune", "Chandigarh"]
}

df = pd.DataFrame(data)
print(df)
```

To load an existing CSV file:

```python
df = pd.read_csv("student_data.csv")
```

### 3.2 Viewing the First and Last Rows

```python
print(df.head())      # First 5 rows
print(df.tail())      # Last 5 rows
print(df.head(3))     # First 3 rows
```

### 3.3 Checking Dataset Dimensions

```python
print("Rows and Columns:", df.shape)
print("Number of Rows:", df.shape[0])
print("Number of Columns:", df.shape[1])
```

### 3.4 Checking Column Names

```python
print(df.columns)
```

### 3.5 Checking Data Types and Non-Null Values

```python
df.info()
```

### 3.6 Generating a Statistical Summary

```python
print(df.describe())
```

For all columns:

```python
print(df.describe(include="all"))
```

### 3.7 Checking Unique Values

```python
print(df["City"].unique())
print("Number of unique cities:", df["City"].nunique())
```

### 3.8 Checking Missing Values

```python
print(df.isnull().sum())
```

## 4. Complete Inspection Program

```python
import pandas as pd

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Karan"],
    "Age": [20, 21, 19, 22, 20],
    "Marks": [78, 92, 65, 88, 74],
    "City": ["Delhi", "Mumbai", "Delhi", "Pune", "Chandigarh"]
}

df = pd.DataFrame(data)

print("First Five Rows:")
print(df.head())

print("\nDataset Shape:")
print(df.shape)

print("\nColumn Names:")
print(df.columns.tolist())

print("\nDataset Information:")
df.info()

print("\nStatistical Summary:")
print(df.describe())

print("\nMissing Values:")
print(df.isnull().sum())
```

## 5. Important Pandas Inspection Functions

| Function | Purpose |
|---|---|
| `head()` | Displays the first rows |
| `tail()` | Displays the last rows |
| `shape` | Returns rows and columns |
| `columns` | Displays column names |
| `info()` | Shows data types and non-null counts |
| `describe()` | Provides statistical summary |
| `isnull().sum()` | Counts missing values |
| `nunique()` | Counts unique values |

## 6. Learning Outcomes

- Learned to load datasets using Pandas.
- Practiced viewing the first and last records.
- Understood dataset dimensions and column names.
- Learned to inspect data types and non-null counts.
- Generated statistical summaries and checked missing values.

## 7. Conclusion

On Day 7, I learned how to inspect a dataset before performing data cleaning and analysis. Pandas inspection functions helped me understand the dataset's structure, data types, statistical properties, and missing values.
