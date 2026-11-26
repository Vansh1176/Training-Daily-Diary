# Day 06 – Data Collection: Primary and Secondary Data

## 1. Objective

To understand data collection, identify different sources of data, and learn the difference between primary and secondary data.

## 2. Introduction

Data collection is the process of gathering information from different sources for analysis. The quality and reliability of collected data affect the results of a data analysis project.

## 3. Topics Covered

### 3.1 Primary Data

Primary data is collected directly by the researcher for a particular purpose.

**Examples:**
- Surveys and questionnaires
- Interviews
- Observations
- Experiments

**Advantages:** It is collected for the specific objective and can be relevant to the study.

**Limitations:** Collection may require more time, effort, and cost.

### 3.2 Secondary Data

Secondary data is information that has already been collected by another person or organization.

**Examples:**
- Government reports
- Research papers
- Public datasets
- Company records
- Websites and published statistics

**Advantages:** It is often quicker and less expensive to obtain.

**Limitations:** It may be outdated, incomplete, or collected for a different purpose.

### 3.3 Difference Between Primary and Secondary Data

| Primary Data | Secondary Data |
|---|---|
| Collected first-hand | Already collected by another source |
| Specific to the current study | May have been collected for another purpose |
| Usually takes more time to collect | Often quicker to obtain |
| Example: conducting a survey | Example: using a published dataset |

### 3.4 Common Data Formats

- CSV – Comma-separated values
- Excel – Spreadsheet files such as XLSX
- JSON – Structured key-value data
- SQL databases – Data stored in relational tables
- Text files – Plain text records

## 4. Practical Implementation

### 4.1 Create a Small Dataset

```python
import pandas as pd

data = {
    "Name": ["Aman", "Priya", "Rahul", "Simran"],
    "Age": [20, 21, 19, 22],
    "Marks": [78, 92, 65, 88]
}

df = pd.DataFrame(data)
print(df)
```

**Expected Output**

```text
     Name  Age  Marks
0    Aman   20     78
1   Priya   21     92
2   Rahul   19     65
3  Simran   22     88
```

### 4.2 Save the Dataset as a CSV File

```python
df.to_csv("student_data.csv", index=False)
print("Dataset saved successfully.")
```

### 4.3 Load the CSV File

```python
loaded_df = pd.read_csv("student_data.csv")
print(loaded_df.head())
```

## 5. Data Collection Considerations

1. Identify the purpose of the analysis.
2. Select a suitable and trustworthy source.
3. Check whether the data is relevant and up to date.
4. Understand the columns, units, and data types.
5. Respect privacy and use data responsibly.

## 6. Learning Outcomes

- Understood the meaning and importance of data collection.
- Differentiated between primary and secondary data.
- Identified common data sources and file formats.
- Practiced creating, saving, and loading a dataset using Pandas.

## 7. Conclusion

On Day 6, I learned how data is collected from primary and secondary sources. I also practiced creating a sample dataset, saving it as a CSV file, and loading it using Pandas.
