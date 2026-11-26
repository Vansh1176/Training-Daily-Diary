# Day 14 – Crosstab and Feature Engineering

## 1. Objective

To understand cross-tabulation and basic feature engineering techniques and learn how to create useful variables from an existing dataset.

## 2. Introduction

Crosstabulation summarizes the relationship between categorical variables by displaying their frequency counts.

Feature engineering is the process of creating, transforming, or selecting features from existing data to make it more useful for analysis and machine learning.

## 3. Topics Covered

- Cross-tabulation
- Frequency tables
- Row and column percentages
- Creating new columns
- Categorizing numerical values
- Extracting date features
- Basic feature transformation

## 4. Practical Dataset

```python
import pandas as pd

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran", "Karan", "Neha"],
    "City": ["Delhi", "Mumbai", "Delhi", "Pune", "Mumbai", "Pune"],
    "Marks": [65, 90, 72, 95, 58, 82],
    "Attendance": [75, 92, 80, 96, 65, 88]
}

df = pd.DataFrame(data)
print(df)
```

## 5. Crosstabulation

### 5.1 Basic Crosstab

First, create a performance category.

```python
df["Performance"] = df["Marks"].apply(
    lambda x: "High" if x >= 80 else "Average"
)

table = pd.crosstab(df["City"], df["Performance"])
print(table)
```

### 5.2 Crosstab with Row Percentages

```python
row_percentages = pd.crosstab(
    df["City"],
    df["Performance"],
    normalize="index"
) * 100

print(row_percentages.round(2))
```

### 5.3 Crosstab with Margins

```python
summary = pd.crosstab(
    df["City"],
    df["Performance"],
    margins=True
)

print(summary)
```

## 6. Feature Engineering

### 6.1 Creating a New Category

```python
df["Grade"] = df["Marks"].apply(
    lambda x: "A" if x >= 85
    else "B" if x >= 70
    else "C"
)

print(df[["Name", "Marks", "Grade"]])
```

### 6.2 Creating a Total or Combined Feature

```python
df["Performance_Score"] = (
    df["Marks"] * 0.8 +
    df["Attendance"] * 0.2
)

print(df[["Name", "Performance_Score"]])
```

### 6.3 Extracting Date Features

```python
dates = pd.DataFrame({
    "Join_Date": pd.to_datetime([
        "2026-01-10",
        "2026-02-15",
        "2026-03-20"
    ])
})

dates["Year"] = dates["Join_Date"].dt.year
dates["Month"] = dates["Join_Date"].dt.month
dates["Day"] = dates["Join_Date"].dt.day

print(dates)
```

## 7. Learning Outcomes

- Understood the purpose of crosstabulation.
- Created frequency tables for categorical variables.
- Calculated row-wise percentages.
- Created new columns from existing data.
- Practiced categorizing numerical values.
- Learned to extract date-related features.

## 8. Conclusion

On Day 14, I learned how to summarize categorical data using crosstabulation and create new features using Pandas. These techniques help reveal patterns and prepare datasets for further analysis and machine learning.
