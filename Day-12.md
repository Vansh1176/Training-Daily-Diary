# Day 12 – Charts and Graphical Representation

## 1. Objective

To learn different types of charts and understand how to select suitable visualizations for different kinds of data.

## 2. Introduction

Charts present data in a visual form so that comparisons and patterns can be understood easily. Different charts are useful for different purposes, such as comparing categories, showing proportions, examining distributions, and observing trends.

## 3. Types of Charts

1. **Line Chart:** Shows trends over time or an ordered sequence.
2. **Bar Chart:** Compares values across categories.
3. **Pie Chart:** Shows proportions of a whole.
4. **Histogram:** Displays the frequency distribution of numerical data.
5. **Scatter Plot:** Shows the relationship between two numerical variables.
6. **Box Plot:** Summarizes spread and helps identify potential outliers.

## 4. Practical Dataset

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    "Subject": ["Python", "DBMS", "OS", "CN", "Maths"],
    "Marks": [85, 78, 90, 82, 88],
    "Students": [30, 28, 32, 25, 27]
}

df = pd.DataFrame(data)
print(df)
```

## 5. Practical Implementation

### 5.1 Line Chart

```python
plt.plot(df["Subject"], df["Marks"], marker="o")
plt.title("Subject-wise Marks Trend")
plt.xlabel("Subject")
plt.ylabel("Marks")
plt.show()
```

### 5.2 Bar Chart

```python
plt.bar(df["Subject"], df["Marks"])
plt.title("Subject-wise Marks")
plt.xlabel("Subject")
plt.ylabel("Marks")
plt.show()
```

### 5.3 Pie Chart

```python
plt.pie(
    df["Students"],
    labels=df["Subject"],
    autopct="%1.1f%%"
)
plt.title("Student Distribution by Subject")
plt.show()
```

### 5.4 Histogram

```python
plt.hist(df["Marks"], bins=5, edgecolor="black")
plt.title("Distribution of Marks")
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.show()
```

### 5.5 Scatter Plot

```python
plt.scatter(df["Students"], df["Marks"])
plt.title("Students vs Marks")
plt.xlabel("Number of Students")
plt.ylabel("Marks")
plt.show()
```

### 5.6 Box Plot

```python
plt.boxplot(df["Marks"])
plt.title("Marks Distribution")
plt.ylabel("Marks")
plt.show()
```

## 6. Choosing the Right Chart

| Requirement | Suitable Chart |
|---|---|
| Show a trend | Line chart |
| Compare categories | Bar chart |
| Show proportions | Pie chart |
| Show numerical distribution | Histogram |
| Examine two numerical variables | Scatter plot |
| Summarize spread and potential outliers | Box plot |

## 7. Learning Outcomes

- Learned different types of charts.
- Created line, bar, pie, histogram, scatter, and box plots.
- Understood how to select charts according to the data.
- Practiced adding labels and titles to visualizations.

## 8. Conclusion

On Day 12, I practiced different graphical techniques using Matplotlib. I learned that selecting the correct chart makes data easier to compare, interpret, and communicate.
