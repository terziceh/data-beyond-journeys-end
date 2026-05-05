# 📊 Data Science Training – Day 5

## Overview

Today focused on **connecting SQL, pandas, statistics, and real-world analytics thinking** into one cohesive skillset.

The emphasis was on:

* Translating logic across tools (SQL → pandas)
* Understanding *why* statistical formulas work
* Applying analysis to real-world business scenarios (utility cost spikes)

---

# 🟦 SQL Practice

### Topics Covered

* `JOIN`
* `GROUP BY`
* Window functions:

  * `LAG()`
  * `PARTITION BY`
  * `ORDER BY`

---

### Key Learnings

* `GROUP BY` defines the **grain (row level)**
* `PARTITION BY` defines **comparison scope**
* `ORDER BY` defines **time logic**
* `LAG()` retrieves **previous value in sequence**

---

### Example Pattern

```sql
WITH sales_agg AS (
    SELECT
        card_id,
        psa_grade,
        sale_date,
        SUM(sale_price) AS total_sales
    FROM sales
    GROUP BY card_id, psa_grade, sale_date
)

SELECT
    c.card_name,
    c.set_name,
    s.*,
    LAG(total_sales) OVER (
        PARTITION BY card_id, psa_grade
        ORDER BY sale_date
    ) AS previous_day_sales
FROM sales_agg s
JOIN cards c
    ON s.card_id = c.card_id;
```

---

### Key Insight

> SQL queries should be written in **steps (CTEs)** to separate logic cleanly:

* Aggregation
* Window functions
* Final calculations

---

### Gaps Identified

* Continue practicing:

  * Multi-step CTE pipelines
  * `LAG()` + % change
  * Complex joins across multiple tables

---

# 🟨 Pandas Practice

### Topics Covered

* `groupby()`
* `.agg()`
* `.shift()` (LAG equivalent)
* `sort_values()`

---

### Key Learnings

```python
df_monthly = (
    df.groupby(['building_name', 'month'])
      .agg(total_month_cost=('cost', 'sum'))
      .reset_index()
)

df_monthly = df_monthly.sort_values(['building_name', 'month'])

df_monthly['previous_month_cost'] = (
    df_monthly
    .groupby('building_name')['total_month_cost']
    .shift(1)
)
```

---

### Key Insight

```text
SQL → Pandas

PARTITION BY → groupby()
ORDER BY → sort_values()
LAG() → shift(1)
```

---

### Important Concept

> `.shift()` works on **row order**, not actual time
> → Must sort first for correct results

---

### Gaps Identified

* More reps with:

  * Time-series transformations
  * Multi-step pipelines
  * Feature engineering patterns

---

# 🟩 Statistics

### Topics Covered

* Confidence Intervals (95%)

---

### Key Learnings

```text
Confidence Interval = mean ± (1.96 × std dev / √n)
```

---

### Concept Breakdown

* **Standard Deviation** → variability in data
* **√n** → reduces uncertainty as sample size increases
* **1.96** → captures 95% of likely outcomes (normal distribution)

---

### Key Insights

* Larger sample size → tighter confidence interval
* Higher variability → wider interval
* Higher confidence → wider interval

---

### Intuition

```text
Confidence Interval =
Best estimate ± uncertainty
```

---

### Real-World Application

> A spike is only meaningful if it falls **outside expected variation**, not just above average.

---

### Gaps Identified

* Need deeper understanding of:

  * Hypothesis testing
  * Statistical significance
  * Applying stats in decision-making

---

# 🧠 Analytics Thinking (Case Study)

### Scenario

* Utility cost spike from $10,200 → $15,000
* Consumption only slightly increased

---

### Analytical Approach

Before concluding a usage issue:

1. **Check fixed vs variable charges**
2. **Calculate cost per kWh**
3. **Investigate external factors**

   * Weather
   * Rate changes
   * Billing adjustments

---

### Key Insight

> Cost spikes ≠ usage spikes
> → Must isolate **price vs consumption vs billing structure**

---

# 🟥 Data Structures & Algorithms (DSA)

### Problem

Find the **first duplicate value** in a list

---

### Solution

```python
def first_duplicate(nums):
    seen = set()
    
    for num in nums:
        if num in seen:
            return num
        seen.add(num)
    
    return None
```

---

### Key Insight

* Use a **set/hashmap** for O(n) duplicate detection
* Check duplicates **during iteration** for “first occurrence”

---

# 📊 Current Skill Assessment

| Skill              | Level    |
| ------------------ | -------- |
| SQL                | 7.8 / 10 |
| Pandas             | 7 / 10   |
| Statistics         | 6.5 / 10 |
| Machine Learning   | 6.5 / 10 |
| Analytics Thinking | 8.5 / 10 |

---

# 🎯 Target (eBay-Level Readiness)

| Skill            | Target   |
| ---------------- | -------- |
| SQL              | 9 / 10   |
| Pandas           | 8.5 / 10 |
| Statistics       | 8 / 10   |
| Machine Learning | 8 / 10   |

---

# 🚧 Key Gaps to Close

### 1. SQL

* Advanced window functions (`LAG`, `LEAD`, rolling metrics)
* Multi-step pipelines (CTEs)
* Complex joins

### 2. Pandas

* Time-series transformations
* Efficient chaining
* Feature engineering

### 3. Statistics

* Hypothesis testing
* Confidence intervals (deeper intuition)
* Business interpretation

### 4. Machine Learning

* Model evaluation beyond RMSE
* Bias vs variance
* Feature importance

---

# 🚀 Plan Moving Forward

### Daily Training Structure

* 2 SQL problems
* 1 pandas problem
* 1 statistics concept
* 1 ML / analytics reasoning question

---

### Next Session (Day 6)

* SQL: `LAG()` + % change + spike detection
* Pandas: rolling averages + anomaly detection
* Statistics: hypothesis testing (A/B tests)
* Case Study: anomaly detection in utility spend

---

# 🔥 Key Takeaway

> Strong data scientists don’t just compute metrics — they understand how data behaves across time, variability, and real-world context.
