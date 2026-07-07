# Day 2 – Introduction to Python, Data Types, Data Structures, Pandas & Data Pipeline

Today, I learned the fundamentals of Python programming and explored how Python is used in data science. I also studied Python data types, data structures, Pandas data structures, the concept of a data pipeline, and data transformation techniques.

---

# Topics Learned

* Introduction to Python
* Data in Python
* Python Data Types
* Python Data Structures
* Pandas Data Structures
* Data Pipeline
* Data Transformation

---

# Introduction to Python

Python is a high-level, interpreted, and object-oriented programming language known for its simple and readable syntax. It is one of the most popular programming languages used in Data Science, Machine Learning, Artificial Intelligence, Web Development, Automation, and Software Development.

### Features of Python

* Easy to learn and use
* Simple and readable syntax
* Open-source and free
* Platform independent
* Large collection of built-in libraries
* Supports Object-Oriented Programming
* Strong community support

### Basic Python Example

```python
print("Hello, World!")
print("Welcome to Python Programming")
```

---

# Data in Python

Data refers to the information that a program stores and processes. Python allows different types of data depending on the nature of the values.

### Example

```python
name = "Rahul"
age = 21
height = 5.8
is_student = True

print(name)
print(age)
print(height)
print(is_student)
```

---

# Python Data Types

Data types specify the kind of value a variable can hold.

## 1. Integer (int)

Stores whole numbers.

```python
age = 20
print(age)
```

Output

```text
20
```

---

## 2. Float (float)

Stores decimal numbers.

```python
price = 99.99
print(price)
```

Output

```text
99.99
```

---

## 3. String (str)

Stores text values.

```python
name = "Python"
print(name)
```

Output

```text
Python
```

---

## 4. Boolean (bool)

Stores logical values.

```python
is_pass = True
print(is_pass)
```

Output

```text
True
```

---

## 5. Complex (complex)

Stores complex numbers.

```python
num = 3 + 5j
print(num)
```

Output

```text
(3+5j)
```

---

# Python Data Structures

Python provides built-in data structures to organize and manage data efficiently.

## 1. List

A list is an ordered and mutable collection.

```python
fruits = ["Apple", "Banana", "Mango"]

print(fruits)
print(fruits[1])
```

Output

```text
['Apple', 'Banana', 'Mango']
Banana
```

### Features

* Ordered
* Mutable
* Allows duplicate values

---

## 2. Tuple

A tuple is an ordered but immutable collection.

```python
colors = ("Red", "Green", "Blue")

print(colors)
```

Output

```text
('Red', 'Green', 'Blue')
```

### Features

* Ordered
* Immutable
* Allows duplicates

---

## 3. Set

A set stores unique values.

```python
numbers = {1, 2, 3, 2, 1}

print(numbers)
```

Output

```text
{1, 2, 3}
```

### Features

* Unordered
* Mutable
* No duplicate elements

---

## 4. Dictionary

A dictionary stores data in key-value pairs.

```python
student = {
    "Name": "Rahul",
    "Age": 20,
    "Course": "Data Science"
}

print(student)
print(student["Name"])
```

Output

```text
{'Name': 'Rahul', 'Age': 20, 'Course': 'Data Science'}
Rahul
```

### Features

* Stores key-value pairs
* Mutable
* Fast data retrieval

---

# Pandas Data Structures

Pandas is a powerful Python library used for data manipulation and analysis.

It mainly provides two data structures:

* Series
* DataFrame

---

## 1. Series

A Series is a one-dimensional labeled array.

```python
import pandas as pd

data = pd.Series([10, 20, 30, 40])

print(data)
```

Output

```text
0    10
1    20
2    30
3    40
dtype: int64
```

---

## 2. DataFrame

A DataFrame is a two-dimensional table consisting of rows and columns.

```python
import pandas as pd

student = {
    "Name": ["Rahul", "Priya", "Aman"],
    "Marks": [85, 92, 78]
}

df = pd.DataFrame(student)

print(df)
```

Output

```text
    Name  Marks
0  Rahul     85
1  Priya     92
2   Aman     78
```

### Advantages of Pandas

* Easy data cleaning
* Fast data manipulation
* Handles missing values
* Supports CSV, Excel, SQL, and JSON files
* Powerful data analysis tools

---

# Data Pipeline

A Data Pipeline is a sequence of processes that collect, move, clean, transform, and prepare data for analysis or machine learning.

### Steps in a Data Pipeline

1. Data Collection
2. Data Ingestion
3. Data Cleaning
4. Data Transformation
5. Data Storage
6. Data Analysis
7. Model Building or Visualization

### Example

Customer data is collected from a website, cleaned using Python and Pandas, transformed into the required format, stored in a database, and then used for dashboard creation or machine learning.

### Benefits

* Automates data processing
* Improves data quality
* Saves time
* Reduces manual errors
* Ensures consistent data flow

---

# Data Transformation

Data Transformation is the process of converting raw data into a clean and usable format for analysis and machine learning.

### Common Data Transformation Techniques

* Removing duplicate records
* Handling missing values
* Changing data types
* Scaling numerical values
* Encoding categorical variables
* Renaming columns
* Filtering unnecessary data

### Example

```python
import pandas as pd

data = {
    "Name": ["Rahul", "Priya", "Aman"],
    "Marks": [85, None, 78]
}

df = pd.DataFrame(data)

df["Marks"] = df["Marks"].fillna(df["Marks"].mean())

print(df)
```

Output

```text
    Name  Marks
0  Rahul   85.0
1  Priya   81.5
2   Aman   78.0

