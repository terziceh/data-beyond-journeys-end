# Applied Data Science Training — Day 2

## Focus of Session

Today's session focused on reinforcing SQL foundations through:

* interview-style questioning
* operational analytics reasoning
* real-world utility analytics examples
* gradual concept stacking
* repetition-based reinforcement

Core philosophy:

```text
Learn → Reinforce → Recall → Apply → Combine → Repeat
```

The goal is not memorization.

The goal is:

* analytical intuition
* business understanding
* operational reasoning
* technical fluency
* production readiness over time

---

# SQL Topics Covered Today

| Topic               | Status                 |
| ------------------- | ---------------------- |
| LIMIT               | ✅ Reinforced           |
| Aggregations        | ✅ Reinforced           |
| NULL Handling       | ✅ Learned              |
| INNER JOIN          | ✅ Learned              |
| String Manipulation | ✅ Learned              |
| Date Manipulation   | ✅ Beginner Foundations |

---

# LIMIT

## Concept Learned

`LIMIT` restricts the number of rows returned.

Used for:

* top-N analysis
* dashboard previews
* debugging
* ranked reporting
* exploratory analysis

### Example

```sql
SELECT
    building_name,
    amount_due
FROM utility_bills
ORDER BY amount_due DESC
LIMIT 5;
```

## Key Insight

```text
ORDER BY happens before LIMIT.
```

This ensures the query returns the actual top records.

---

# Aggregations Reinforcement

## Aggregations Reviewed

* SUM()
* AVG()
* COUNT()
* MIN()
* MAX()

## Operational Understanding

Aggregations convert:

```text
row-level detail → business summaries
```

Examples:

* total utility spend
* average utility bill
* provider-level summaries
* invoice counts
* total consumption

### Example

```sql
SELECT
    provider,
    SUM(amount_due) AS total_spend
FROM utility_bills
GROUP BY provider;
```

---

# COUNT() Understanding

## COUNT(*)

Counts:

```text
all rows
```

## COUNT(column_name)

Counts:

```text
non-null values only
```

## Operational Importance

This matters for:

* incomplete invoices
* missing IDs
* broken parsing
* ETL validation
* KPI accuracy

---

# NULL Handling

## Core Concept

NULL represents:

```text
missing / unknown values
```

NOT:

* 0
* blank text
* false

---

## Syntax Learned

### Correct NULL Checking

```sql
WHERE invoice_id IS NULL
```

### Correct NON-NULL Checking

```sql
WHERE invoice_id IS NOT NULL
```

### Incorrect Syntax

```sql
WHERE invoice_id = NULL
```

---

## Operational Uses

NULL handling is critical for:

* forecasting datasets
* invoice parsing
* ETL pipelines
* OCR extraction
* dashboard accuracy
* data quality validation

---

# INNER JOIN

## Concept Learned

INNER JOIN combines tables using a shared key.

### Example

```sql
SELECT
    b.building_name,
    u.amount_due
FROM utility_bills u
JOIN buildings b
ON u.building_id = b.building_id;
```

---

## Key Insight

```text
INNER JOIN only returns matching rows.
```

If a key does not exist in both tables:

```text
that row disappears from the result.
```

---

## Operational Understanding

This matters because joins can:

* accidentally remove records
* corrupt KPIs
* break dashboards
* reduce forecasting data
* cause undercounting

---

# String Manipulation

## Functions Learned

| Function | Purpose               |
| -------- | --------------------- |
| UPPER()  | standardize uppercase |
| LOWER()  | standardize lowercase |
| TRIM()   | remove extra spaces   |
| CONCAT() | combine text          |
| LIKE     | pattern matching      |

---

# UPPER() / LOWER()

## Operational Insight

Different capitalizations create separate analytical groups.

Example:

| provider        |
| --------------- |
| Dominion Energy |
| dominion energy |
| DOMINION ENERGY |

Without standardization:

```text
GROUP BY creates multiple incorrect categories.
```

### Example

```sql
SELECT
    LOWER(provider) AS provider_clean,
    SUM(amount_due)
FROM utility_bills
GROUP BY LOWER(provider);
```

---

# TRIM()

## Purpose

Removes hidden leading/trailing spaces.

### Example

```sql
SELECT
    TRIM(provider)
FROM utility_bills;
```

## Operational Importance

Hidden spaces can:

* break joins
* split aggregations
* corrupt dashboard totals
* reduce match rates

---

# CONCAT()

## Purpose

Combines strings together.

### Example

```sql
SELECT
    CONCAT(building_name, ' - ', provider) AS building_provider
FROM utility_bills;
```

## Use Cases

* dashboard labels
* reporting text
* export formatting
* descriptive categories

---

# LIKE

## Purpose

Pattern matching.

### Example

```sql
WHERE LOWER(provider) LIKE '%dominion%'
```

---

## Wildcard Patterns

| Pattern   | Meaning          |
| --------- | ---------------- |
| 'Dom%'    | starts with Dom  |
| '%Energy' | ends with Energy |
| '%Power%' | contains Power   |

---

## Operational Use Cases

LIKE is commonly used for:

* OCR cleanup
* invoice categorization
* exploratory analysis
* filtering inconsistent provider names
* text-based analytics

---

# Beginner Date Manipulation

## Functions Learned

| Function     | Purpose                  |
| ------------ | ------------------------ |
| YEAR()       | extract year             |
| MONTH()      | extract month            |
| DAY()        | extract day              |
| CURRENT_DATE | today's date             |
| DATEDIFF()   | difference between dates |

---

# YEAR()

### Example

```sql
SELECT
    YEAR(invoice_date) AS bill_year
FROM utility_bills;
```

## Use Cases

* annual trends
* yearly KPIs
* long-term forecasting

---

# MONTH()

### Example

```sql
SELECT
    MONTH(invoice_date) AS bill_month
FROM utility_bills;
```

## Use Cases

* seasonality analysis
* monthly reporting
* utility consumption trends

## Key Insight

```text
MONTH() is more useful than YEAR() for seasonal analysis.
```

---

# DATEDIFF()

### Example

```sql
SELECT
    DATEDIFF(CURRENT_DATE, invoice_date) AS days_since
FROM utility_bills;
```

## Operational Uses

* invoice aging
* overdue analysis
* stale data detection
* billing cadence analysis

---

# Biggest Learning Outcome

The biggest improvement from today's session was:

```text
understanding WHY the functions matter operationally
```

Instead of simply memorizing syntax.

Key growth areas:

* understanding how dirty data affects analytics
* recognizing how joins can remove data
* understanding how inconsistent text corrupts KPIs
* connecting SQL functions to forecasting and dashboards
* improving interview-style reasoning

---

# Current SQL Foundation Progress

## Completed SQL Topics

| Topic                      | Status |
| -------------------------- | ------ |
| SELECT                     | ✅      |
| FROM                       | ✅      |
| WHERE                      | ✅      |
| ORDER BY                   | ✅      |
| GROUP BY                   | ✅      |
| HAVING                     | ✅      |
| LIMIT                      | ✅      |
| Aggregations               | ✅      |
| NULL Handling              | ✅      |
| INNER JOIN                 | ✅      |
| String Manipulation        | ✅      |
| Beginner Date Manipulation | ✅      |
| Arithmetic Operators       | ✅      |

---

# Next SQL Topics

Planned progression:

* LEFT JOIN
* CASE WHEN
* pandas groupby
* missing values in pandas
* merges in pandas
* datetime handling in pandas
* exploratory analysis
* CTEs
* window functions later

---

# Databricks Forecasting Project Planning

## Goal

Build a production-style utility forecasting analytics pipeline using:

* SQL Server
* Databricks
* Spark
* Delta Tables
* Python forecasting
* Power BI

---

# Planned Architecture

```text
SQL Server Source Data
        ↓
Databricks Bronze Layer
(raw ingestion)
        ↓
Databricks Silver Layer
(cleaning + transformations)
        ↓
Databricks Gold Layer
(aggregated forecasting tables)
        ↓
Python Forecasting Models
(ARIMA/SARIMA/rolling trends)
        ↓
Power BI Dashboard
```

---

# Planned Forecasting KPIs

* Total Utility Spend
* Total Consumption
* Cost per kWh
* Monthly Consumption Trend
* Seasonal Utility Trends
* Forecasted Consumption
* Forecasted Spend
* Variance from Forecast
* Building-Level Trend Analysis

---

# Databricks Learning Focus

Initial beginner focus:

* Spark DataFrames
* Delta Tables
* Bronze/Silver/Gold architecture
* SQL transformations in Databricks
* connecting Databricks to Power BI
* simple forecasting pipelines

Advanced concepts later:

* partitioning
* orchestration
* streaming
* optimization
* production scheduling
* cloud deployment

---

# Overall Reflection

Today's session showed:

```text
operational analytics intuition is developing faster than syntax memorization.
```

Main improvement areas:

* SQL syntax fluency
* remembering grouping rules
* pandas fluency next
* gradual transition into Databricks and Spark

Main strengths:

* business reasoning
* forecasting intuition
* operational understanding
* understanding WHY analytics systems matter
* connecting technical concepts to real utility operations
