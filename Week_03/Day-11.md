# Day 11 – Introduction to Data Visualization and Matplotlib

## 1. Objective

To understand data visualization and learn how to create basic charts using Python's Matplotlib library.

## 2. Introduction

Data visualization is the graphical representation of information and data. It helps communicate patterns, trends, comparisons, and relationships through charts and graphs.

Matplotlib is a popular Python library used to create static, animated, and interactive visualizations.

## 3. Topics Covered

- Meaning and importance of data visualization
- Introduction to Matplotlib
- Figure and axes
- Figure size
- Chart title and axis labels
- Displaying plots

## 4. Installing and Importing Matplotlib

```python
!pip install matplotlib
```

```python
import matplotlib.pyplot as plt
```

## 5. Practical Implementation

### 5.1 Create a Simple Line Plot

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May"]
sales = [120, 150, 135, 180, 200]

plt.plot(months, sales)
plt.title("Monthly Sales")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.show()
```

### 5.2 Customize Figure Size

```python
plt.figure(figsize=(8, 4))
plt.plot(months, sales, marker="o")
plt.title("Monthly Sales Trend")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.show()
```

### 5.3 Add Grid and Markers

```python
plt.figure(figsize=(8, 4))
plt.plot(months, sales, marker="o")
plt.title("Sales with Grid")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.grid(True)
plt.show()
```

### 5.4 Create a Bar Plot

```python
subjects = ["Python", "DBMS", "OS", "CN"]
marks = [85, 78, 90, 82]

plt.bar(subjects, marks)
plt.title("Subject-wise Marks")
plt.xlabel("Subjects")
plt.ylabel("Marks")
plt.show()
```

## 6. Important Matplotlib Functions

| Function | Purpose |
|---|---|
| `plt.figure()` | Creates a figure |
| `plt.plot()` | Creates a line plot |
| `plt.bar()` | Creates a bar chart |
| `plt.title()` | Adds a chart title |
| `plt.xlabel()` | Labels the X-axis |
| `plt.ylabel()` | Labels the Y-axis |
| `plt.grid()` | Displays grid lines |
| `plt.show()` | Displays the chart |

## 7. Learning Outcomes

- Understood the importance of data visualization.
- Learned to import Matplotlib.
- Created line and bar charts.
- Practiced adding titles, labels, markers, and grids.
- Learned how to control figure size.

## 8. Conclusion

On Day 11, I learned the basics of data visualization using Matplotlib. I created simple charts and practiced adding titles, axis labels, markers, and grid lines to make visualizations easier to understand.
