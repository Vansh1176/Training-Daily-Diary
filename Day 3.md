# Day 3 – Data Cleaning and Data Preprocessing Using Pandas

Today, I learned about **Data Cleaning**, one of the most important steps in the data analysis and machine learning workflow. I explored how to inspect datasets using Pandas functions, identify and handle missing values, detect and remove duplicate records, and understand the concept of outliers.

---

# Topics Learned

* Data Cleaning
* Importance of Data Cleaning
* Pandas Functions: `head()`, `info()`, `describe()`
* Missing Values
* Counting Missing Values
* Methods to Handle Missing Values
* Counting Duplicate Rows
* Removing Duplicate Rows
* Outliers

---

# Data Cleaning

Data Cleaning is the process of identifying and correcting inaccurate, incomplete, duplicate, or inconsistent data. Clean data improves the quality of analysis and helps build accurate machine learning models.

### Why is Data Cleaning Important?

* Improves data quality
* Increases model accuracy
* Removes inconsistencies
* Reduces errors during analysis
* Makes data reliable and meaningful
* Saves time during model development

---

# Loading a Dataset

Before cleaning data, we first load it using Pandas.

```python
import pandas as pd

df = pd.read_csv("students.csv")
```

---

# Pandas Functions for Data Inspection

## 1. `head()`

The `head()` function displays the first five rows of the dataset by default.

### Syntax

```python
df.head()
```

### Example

```python
print(df.head())
```

This helps quickly understand the structure of the dataset.

---

## 2. `info()`

The `info()` function provides a summary of the dataset.

It displays:

* Number of rows and columns
* Column names
* Data types
* Number of non-null values
* Memory usage

### Example

```python
df.info()
```

---

## 3. `describe()`

The `describe()` function generates statistical information for numerical columns.

It shows:

* Count
* Mean
* Standard Deviation
* Minimum Value
* Maximum Value
* Quartiles (25%, 50%, 75%)

### Example

```python
df.describe()
```

This function is useful for understanding the distribution of numerical data.

---

# Missing Values

Missing values are empty or unavailable values in a dataset.

They are usually represented as:

* `NaN` (Not a Number)
* `None`
* Blank cells

### Example

| Name  | Age | Marks |
| ----- | --- | ----- |
| Rahul | 20  | 85    |
| Priya | 21  | NaN   |
| Aman  | 22  | 78    |

Here, Priya's marks are missing.

---

# Counting Missing Values

Use `isnull()` along with `sum()` to count missing values in each column.

### Example

```python
df.isnull().sum()
```

### Sample Output

```text
Name      0
Age       0
Marks     1
dtype: int64
```

To count the total missing values in the dataset:

```python
df.isnull().sum().sum()
```

---

# Methods to Handle Missing Values

There are several techniques to handle missing data depending on the situation.

## 1. Remove Rows with Missing Values

```python
df.dropna()
```

---

## 2. Remove Columns with Missing Values

```python
df.dropna(axis=1)
```

---

## 3. Fill Missing Values with a Constant

```python
df.fillna(0)
```

---

## 4. Fill Missing Values with Mean

```python
df["Marks"] = df["Marks"].fillna(df["Marks"].mean())
```

---

## 5. Fill Missing Values with Median

```python
df["Marks"] = df["Marks"].fillna(df["Marks"].median())
```

---

## 6. Fill Missing Values with Mode

```python
df["City"] = df["City"].fillna(df["City"].mode()[0])
```

### Choosing the Right Method

* **Mean**: Suitable for normally distributed numerical data.
* **Median**: Better when data contains outliers.
* **Mode**: Best for categorical data.
* **Drop Rows/Columns**: Use only when the missing data is minimal or not important.

---

# Duplicate Rows

Duplicate rows are records that appear more than once in a dataset.

Duplicate data can lead to incorrect analysis and biased machine learning models.

---

# Counting Duplicate Rows

Use the `duplicated()` function to identify duplicate records.

### Example

```python
df.duplicated().sum()
```

### Sample Output

```text
5
```

This means there are 5 duplicate rows in the dataset.

---

# Removing Duplicate Rows

Use the `drop_duplicates()` function to remove duplicate records.

### Example

```python
df = df.drop_duplicates()
```

Or,

```python
df.drop_duplicates(inplace=True)
```

---

# Outliers

Outliers are data points that are significantly different from the rest of the observations.

They may occur because of:

* Data entry errors
* Measurement errors
* Natural variation
* Rare events

### Example

| Student | Marks |
| ------- | ----: |
| A       |    82 |
| B       |    85 |
| C       |    84 |
| D       |    83 |
| E       |   250 |

Here, **250** is an outlier because it is far from the other values.

---

# Why Outliers Matter

* Can reduce machine learning model accuracy
* Distort statistical measures such as mean
* Affect data visualization
* Lead to incorrect conclusions

---

# Common Methods to Detect Outliers

* Box Plot
* Interquartile Range (IQR)
* Z-Score Method
* Scatter Plot

These methods help identify unusually high or low values before model training.

---

# Key Takeaways

* Learned the importance of data cleaning in data science.
* Explored dataset inspection using `head()`, `info()`, and `describe()`.
* Understood missing values and how to count them.
* Learned multiple methods to handle missing values.
* Identified and removed duplicate rows using Pandas.
* Understood the concept of outliers and their impact on data analysis and machine learning.
