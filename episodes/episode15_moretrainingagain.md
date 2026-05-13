# Python/pandas Training — Level 1 Foundations (Day Progress)

## Goal
Develop strong foundational pandas and analytics skills focused on:

- loading data
- cleaning datasets
- filtering and transforming data
- handling missing values
- datatype conversions
- exploratory analysis
- SQL ↔ pandas translation
- operational analytics thinking

Primary focus:
- pandas
- dataframe manipulation
- preprocessing workflows
- analytics foundations

---

# Topics Covered

| Topic | Status |
|---|---|
| Importing Libraries | ✅ Complete |
| Reading CSVs and Files | ✅ Complete |
| Viewing Data | ✅ Complete |
| Selecting Columns | ✅ Complete |
| Filtering Rows | ✅ Complete |
| Renaming Columns | 🔄 Started |
| Changing Data Types | ✅ Complete |
| Exploring Data | 🔄 In Progress |
| Handling Missing Values | ✅ Complete |
| Basic Charts and Visualizations | ⬜ Not Started |
| Basic String Manipulation | ⬜ Not Started |

---

# Core pandas Concepts Learned

## Importing Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
````

---

# Reading CSV Files

```python
df = pd.read_csv("file.csv")
```

---

# Viewing Data

```python
df.head()
df.info()
df.describe()
df.dtypes
```

### Purpose

* inspect dataframe structure
* inspect datatypes
* inspect missing values
* inspect statistical summaries

---

# Selecting Columns

## Single Column

```python
df['column']
```

## Multiple Columns

```python
df[['column1', 'column2']]
```

---

# Filtering Rows

## SQL Example

```sql
SELECT *
FROM utilities
WHERE provider = 'Dominion'
```

## pandas Equivalent

```python
utilities[
    utilities['provider'] == 'Dominion'
]
```

---

# Multiple Conditions

```python
utilities[
    (utilities['provider'] == 'Dominion') &
    (utilities['amount_due'] > 5000)
]
```

### Key Lessons

* use `==` for equality
* use `&` for AND conditions
* each condition requires parentheses
* dataframe filtering uses `[]`, not `()`

---

# Selecting + Filtering + Sorting Workflow

```python
utilities_filtered = utilities[
    (utilities['provider'] == 'VCU') &
    (utilities['amount_due'] > 1000)
][['building_name', 'amount_due', 'provider']].sort_values(
    by='amount_due',
    ascending=False
)
```

### Important Pattern Learned

```python
df[(rows)][[columns]].sort_values(...)
```

---

# GroupBy + Aggregations

## SQL Example

```sql
SELECT provider, AVG(amount_due)
FROM utilities
GROUP BY provider
```

## pandas Equivalent

```python
utilities.groupby('provider', as_index=False).agg(
    average_amount=('amount_due', 'mean')
)
```

---

# Datatype Conversions

## Checking Datatypes

```python
utilities.info()
utilities.dtypes
```

---

# Converting Currency Strings → Float

## Example Raw Data

```python
'$1,200.50'
```

## Cleaning + Conversion

```python
utilities['amount_due'] = (
    utilities['amount_due']
        .str.replace(',', '', regex=False)
        .str.replace('$', '', regex=False)
        .astype(float)
)
```

---

# Converting Strings → Integer

```python
utilities['consumption_kwh'] = (
    utilities['consumption_kwh']
        .str.strip()
        .astype(int)
)
```

---

# Converting Dates → Datetime

```python
utilities['invoice_date'] = pd.to_datetime(
    utilities['invoice_date']
)
```

---

# Datatype Lessons Learned

### Core Datatypes

| Datatype   | Meaning          |
| ---------- | ---------------- |
| object     | text/string      |
| int64      | integers         |
| float64    | decimals         |
| datetime64 | dates/timestamps |
| bool       | true/false       |

### Operational Understanding

Proper datatypes are critical for:

* forecasting models
* dashboard calculations
* KPIs
* aggregations
* time-series analysis
* filtering/grouping

---

# Handling Missing Values

## Checking Missing Values

```python
utilities.isna().sum()
```

---

# Returning Rows With Missing Values

```python
utilities[
    utilities['amount_due'].isna()
]
```

---

# Dropping Missing Rows

## Drop rows where invoice_date is missing

```python
utilities = utilities.dropna(
    subset=['invoice_date']
)
```

---

# Filling Missing Values

## Fill Missing Text Values

```python
utilities['building_name'] = (
    utilities['building_name'].fillna(
        'Unknown Building'
    )
)
```

---

## Fill Missing Numeric Values

```python
utilities['amount_due'] = (
    utilities['amount_due'].fillna(
        utilities['amount_due'].mean()
    )
)
```

---

# Important pandas Pattern Learned

```python
df['column'] = df['column'].something()
```

Examples:

```python
df['amount_due'] = df['amount_due'].fillna(0)

df['invoice_date'] = pd.to_datetime(df['invoice_date'])

df['provider'] = df['provider'].str.lower()
```

---

# Missing Value Operational Thinking

### Important Lesson

Not all missing values should be handled the same way.

| Column         | Possible Action                    |
| -------------- | ---------------------------------- |
| building_name  | fill with Unknown                  |
| invoice_date   | likely drop                        |
| amount_due     | investigate/fill carefully         |
| provider       | potentially dangerous for grouping |
| account_number | may still preserve useful row      |

### Analyst Lesson

Blindly dropping or filling missing values can:

* distort KPIs
* break forecasts
* reduce data accuracy
* remove valid operational information

---

# Applied Statistics Foundations

| Concept            | Status |
| ------------------ | ------ |
| Mean               | ✅      |
| Median             | ✅      |
| Mode               | ✅      |
| Variance           | ✅      |
| Standard Deviation | ✅      |

---

# Statistics Operational Understanding

## Mean

Average value across all entries.

```python
utilities['amount_due'].mean()
```

---

## Median

Middle value in sorted dataset.

```python
utilities['amount_due'].median()
```

---

## Standard Deviation

Measures spread/variation around the mean.

```python
utilities['amount_due'].std()
```

### Operational Meaning

High standard deviation in utility costs may indicate:

* unstable usage
* abnormal spending
* building inefficiencies
* seasonal variability

---

# Key pandas Concepts Reinforced

* dataframe filtering
* multiple condition filtering
* sorting
* grouping
* named aggregations
* datatype inspection
* datatype conversion
* missing value analysis
* operational dataset thinking
* SQL ↔ pandas translation

---

# Next Session Topics

## Exploring Data

* value_counts()
* unique()
* nunique()
* correlation basics
* distributions

## Basic Charts & Visualization

* matplotlib basics
* bar charts
* histograms
* line charts
* analyst storytelling

## Basic String Manipulation

* .str.lower()
* .str.upper()
* .str.contains()
* .str.replace()
* .str.strip()

---

# Long-Term Goal

Apply Level 1 SQL + pandas foundations into a real statistical analytics project involving:

* exploratory analysis
* preprocessing
* KPI development
* statistical interpretation
* forecasting preparation
* operational/business storytelling

