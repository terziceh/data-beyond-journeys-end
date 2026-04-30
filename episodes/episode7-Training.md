
````markdown
# 📊 Data Science Interview Training – Day 1

## Overview

Today I restarted my structured data science interview training. The goal is to practice for one hour at the start of each workday, focusing on the core skills needed for data analyst, analytics engineering, and entry-level data science roles.

### Daily Focus Areas
- SQL
- Python (pandas)
- Statistics & Machine Learning Concepts

---

## 🧠 SQL Practice

### Topics Covered
- `GROUP BY`
- `HAVING`
- Aggregations: `SUM()`, `COUNT()`
- Date filtering
- `ORDER BY` + `LIMIT`
- Common Table Expressions (CTEs)
- Window functions: `RANK()`, `ROW_NUMBER()`, `DENSE_RANK()`

---

### Key Patterns

#### Basic Aggregation Pattern
```sql
SELECT column, SUM(metric), COUNT(*)
FROM table
WHERE condition
GROUP BY column
HAVING COUNT(*) >= threshold
ORDER BY metric DESC
LIMIT N;
````

#### CTE + Ranking Pattern

```sql
WITH base AS (
    SELECT
        column,
        SUM(metric) AS total_metric,
        COUNT(*) AS count_metric
    FROM table
    WHERE condition
    GROUP BY column
),
ranked AS (
    SELECT
        *,
        RANK() OVER (ORDER BY total_metric DESC) AS rank
    FROM base
)
SELECT *
FROM ranked
WHERE rank <= N;
```

---

### Key Takeaways

* `WHERE` filters rows **before aggregation**
* `HAVING` filters **after aggregation**
* Window functions are used for **ranking within datasets**

#### Ranking Functions

```sql
RANK() OVER (ORDER BY metric DESC)
```

* `RANK()` → allows ties, skips numbers
* `ROW_NUMBER()` → no ties, always unique ranking
* `DENSE_RANK()` → allows ties, no gaps in ranking

---

## 🐍 Python / pandas Practice

### Topics Covered

* `groupby`
* `.agg()` (multi-aggregation)
* Filtering after aggregation
* Sorting with `.sort_values()`
* `.head()` for Top N
* `.reset_index()`
* Intro to per-group ranking

---

### Core pandas Pattern

```python
result = (
    df.groupby('column')
      .agg(
          metric_1=('value_column', 'mean'),
          metric_2=('value_column', 'count')
      )
      .reset_index()
)

result = (
    result[result['metric_2'] >= threshold]
    .sort_values(['metric_1', 'metric_2'], ascending=[False, False])
    .head(N)
)
```

---

### Key Takeaways

* pandas `groupby + agg` = SQL `GROUP BY`
* Filtering after aggregation = SQL `HAVING`
* Sorting + `.head()` = SQL `ORDER BY + LIMIT`

#### Important Habit

Always use:

```python
.reset_index()
```

to keep grouped columns accessible.

---

### Advanced Concept Introduced

* Ranking **within groups** (similar to SQL window functions)

Example:

```python
df.groupby('group')['metric'].rank(...)
```

Used for:

* Top N per category
* Feature engineering
* Recommendation systems

---

## 📊 Statistics Practice

### Mean, Median, Mode

* **Mean** → Average of all values
* **Median** → Middle value when sorted
* **Mode** → Most frequent value

---

### When to Use Each

* Use **Mean** → when data is symmetric and clean
* Use **Median** → when data has outliers or is skewed
* Use **Mode** → for most common category/value

---

### Key Insight

Median is the most reliable when outliers exist.

Example:

```text
[10, 12, 13, 15, 1000]
```

* Mean = heavily skewed ❌
* Median = represents typical value ✅

---

## 🤖 Machine Learning Concept

### Overfitting

Overfitting occurs when a model learns the training data too closely, including noise and non-generalizable patterns.

> The model memorizes instead of learning.

---

### Clean Interview Answer

> Overfitting occurs when a model performs very well on training data but poorly on unseen data because it learned noise instead of general patterns.

---

### How to Prevent Overfitting

* Cross-validation
* Regularization
* Simpler models
* More data

---

## 🧠 Reflection

Today’s session focused on building strong foundational patterns across SQL, pandas, and statistics.

### Self-Assessment

* Logic → Strong
* Syntax → Needs polishing
* Interview explanations → Improving

---

## 🚀 Next Steps

Planned focus for next session:

* SQL → Deeper window functions
* pandas → Joins + feature engineering
* Stats → Probability & distributions

---

## 💡 Goal

Build consistency and repetition until:

* SQL becomes automatic
* pandas workflows feel natural
* statistical explanations are clear and confident


