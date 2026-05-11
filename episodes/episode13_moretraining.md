
# Applied Data Science Training System

## Overview

This training system is built around:

```text
Learn → Reinforce → Recall → Apply → Combine → Repeat
````

The goal is to develop:

* instant recall
* analytical intuition
* pattern recognition
* project execution skills
* real-world data problem solving

This is not passive learning.

The goal is to answer realistic analytics and machine learning questions completely from memory.

---

# Current Focus

Current progression:

```text
SQL Foundations →
pandas Foundations →
Applied Statistics →
Project Integration
```

Core philosophy:

```text
Master the foundations deeply.
Use projects to learn advanced tooling naturally.
```

---

# SQL Level 1 — Foundations

## Goal

Become fully comfortable:

* retrieving
* filtering
* summarizing
* and analyzing relational data entirely from memory.

### Benchmark

Open a dataset and independently answer realistic analysis questions using SQL.

---

# SQL Level 1 Topics

| Topic                | Status        |
| -------------------- | ------------- |
| SELECT               | ✅ Complete    |
| FROM                 | ✅ Complete    |
| WHERE                | ✅ Complete    |
| ORDER BY             | ✅ Complete    |
| GROUP BY             | ✅ Complete    |
| HAVING               | ✅ Complete    |
| LIMIT                | ⬜ Not Started |
| Aggregations         | ✅ Complete    |
| NULL Handling        | ⬜ Not Started |
| Basic Joins          | ⬜ Not Started |
| String Manipulation  | ⬜ Not Started |
| Date Manipulation    | ⬜ Not Started |
| Arithmetic Operators | ✅ Complete    |

---

# SQL Concepts Learned

## SELECT

* selecting columns
* selecting all columns
* aliases
* calculated columns
* output shaping

## WHERE

* filtering rows
* AND / OR
* BETWEEN
* IN

## ORDER BY

* ascending vs descending
* multi-column sorting

## GROUP BY

* grouped analysis
* aggregations
* summarization

## HAVING

* filtering grouped results
* post-aggregation filtering

---

# SQL Analytical Flow

```text
SELECT →
FROM →
WHERE →
GROUP BY →
HAVING →
ORDER BY
```

---

# Python/pandas Level 1 — Foundations

## Goal

Become fully comfortable:

* loading
* cleaning
* exploring
* transforming
* and analyzing datasets with Python.

Primary focus:

* pandas
* dataframe manipulation
* exploratory analysis
* SQL ↔ pandas mapping

---

# Python Level 1 Topics

| Topic                           | Status         |
| ------------------------------- | -------------- |
| Importing Libraries             | ✅ Complete     |
| Reading CSVs and Files          | ✅ Complete     |
| Viewing Data                    | ✅ Complete     |
| Selecting Columns               | ✅ Complete     |
| Filtering Rows                  | ✅ Complete     |
| Renaming Columns                | ⬜ Not Started  |
| Changing Data Types             | ⬜ Not Started  |
| Exploring Data                  | 🔄 In Progress |
| Handling Missing Values         | ⬜ Not Started  |
| Basic Charts and Visualizations | ⬜ Not Started  |
| Basic String Manipulation       | ⬜ Not Started  |

---

# pandas Concepts Learned

## Importing Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

---

## Reading CSV Files

```python
df = pd.read_csv("file.csv")
```

---

## Viewing Data

```python
df.head()
df.info()
df.describe()
```

---

## Selecting Columns

Single column:

```python
df['column']
```

Multiple columns:

```python
df[['column1', 'column2']]
```

---

## Filtering Rows

SQL:

```sql
SELECT *
FROM employees
WHERE salary > 80000
```

pandas equivalent:

```python
employees_df[employees_df['salary'] > 80000]
```

Multiple conditions:

```python
employees_df[
    (employees_df['department'] == 'Finance') &
    (employees_df['salary'] > 70000)
]
```

---

# Applied Statistics Foundations

## Goal

Understand:

* what statistics represent
* how to interpret them operationally
* how to apply them in SQL and pandas

---

# Descriptive Statistics Covered

| Concept            | Status     |
| ------------------ | ---------- |
| Mean               | ✅ Complete |
| Median             | ✅ Complete |
| Mode               | ✅ Complete |
| Variance           | ✅ Complete |
| Standard Deviation | ✅ Complete |

---

# Statistical Intuition Learned

## Mean

Average value across observations.

## Median

Middle value in a sorted dataset.
Useful for resisting outliers.

## Mode

Most common value in a dataset.

## Variance

Measures how spread out values are from the mean.

## Standard Deviation

Measures the typical distance values are from the mean.

---

# Core Analytics Philosophy

The goal is NOT to memorize formulas.

The goal is to understand:

```text
“What does the behavior of this dataset actually mean?”
```

---

# Current Project Stack

1. Invoice Automation System
2. Movie Recommender System
3. Utilities Forecasting & Dashboarding
4. Pokémon Market Intelligence System

These projects serve as:

* application environments
* portfolio pieces
* advanced learning systems

---

# Next Training Session

## SQL Review Test

* SELECT
* WHERE
* ORDER BY
* GROUP BY
* HAVING

## pandas Review Test

* loading data
* viewing data
* selecting columns
* filtering rows

## Statistics Review Test

* mean
* median
* mode
* variance
* standard deviation

Then continue into:

* joins
* missing values
* grouping in pandas
* exploratory analysis
* applied statistics

---
