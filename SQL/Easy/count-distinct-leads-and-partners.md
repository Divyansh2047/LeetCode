# #1693 Count Distinct Leads and Partners

## 🧩 Problem Statement

Given a table **DailySales**:

| Column Name | Type |
|------------|------|
| date_id | date |
| make_name | varchar |
| lead_id | int |
| partner_id | int |

- The table may contain duplicate rows.
- Each row represents a product sold on a specific date to a lead and partner.

### 🎯 Task

For each `date_id` and `make_name`, find:

- Number of distinct `lead_id`
- Number of distinct `partner_id`

Return the result in any order.

---

## 📊 Example

### Input

| date_id | make_name | lead_id | partner_id |
|--------|-----------|---------|------------|
| 2020-12-8 | toyota | 0 | 1 |
| 2020-12-8 | toyota | 1 | 0 |
| 2020-12-8 | toyota | 1 | 2 |
| 2020-12-7 | toyota | 0 | 2 |
| 2020-12-7 | toyota | 0 | 1 |
| 2020-12-8 | honda | 1 | 2 |
| 2020-12-8 | honda | 2 | 1 |
| 2020-12-7 | honda | 0 | 1 |
| 2020-12-7 | honda | 1 | 2 |
| 2020-12-7 | honda | 2 | 1 |

### Output

| date_id | make_name | unique_leads | unique_partners |
|--------|-----------|--------------|-----------------|
| 2020-12-8 | toyota | 2 | 3 |
| 2020-12-7 | toyota | 1 | 2 |
| 2020-12-8 | honda | 2 | 2 |
| 2020-12-7 | honda | 3 | 2 |

---

## 🧠 Intuition

The table contains duplicate entries for leads and partners.

Example:

Toyota on 2020-12-8 has leads:

```
0, 1, 1
```

Unique leads:

```
0, 1
```

Count = 2

Similarly, partners:

```
1, 0, 2
```

Unique partners:

```
0, 1, 2
```

Count = 3

So we need:

> Count distinct lead_id and partner_id for each date_id and make_name

---

## ⚙️ Approach

### Step 1
Group data by `date_id` and `make_name`

### Step 2
Count distinct `lead_id`

### Step 3
Count distinct `partner_id`

### Step 4
Return the result

SQL concepts used:

- GROUP BY
- COUNT DISTINCT
- Aggregation

---

## 🛠️ Method Used

### 1️⃣ GROUP BY

Groups rows by:

```
date_id
make_name
```

This creates separate groups for each product on each date.

---

### 2️⃣ COUNT(DISTINCT)

Removes duplicate values.

Example:

```
1, 1, 2 → 1, 2
```

Count = 2

---

## 💻 SQL Solution

```sql
SELECT 
    date_id, 
    make_name,
    COUNT(DISTINCT lead_id) AS unique_leads,
    COUNT(DISTINCT partner_id) AS unique_partners
FROM DailySales
GROUP BY date_id, make_name;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the DailySales table
- GROUP BY processes each row once

---

### Space Complexity

O(1)

- No extra memory used
- Only aggregation

---

## 🧪 Dry Run

### 2020-12-8 Toyota

Leads:

```
0
1
1
```

Unique:

```
0, 1
```

Count = 2

Partners:

```
1
0
2
```

Count = 3

---

### 2020-12-7 Honda

Leads:

```
0
1
2
```

Count = 3

Partners:

```
1
2
```

Count = 2

---

## 📚 Learning

- GROUP BY helps in grouping records
- COUNT DISTINCT removes duplicates
- Useful in database analytics
- Common SQL interview question
- Helps in aggregation-based queries

---

## 🏁 Final Output

| date_id | make_name | unique_leads | unique_partners |
|--------|-----------|--------------|-----------------|
| 2020-12-8 | toyota | 2 | 3 |
| 2020-12-7 | toyota | 1 | 2 |
| 2020-12-8 | honda | 2 | 2 |
| 2020-12-7 | honda | 3 | 2 |

---

## 🔗 Related Concepts

- SQL Aggregation
- GROUP BY
- COUNT DISTINCT
- Database Queries
- Data Analysis

---

## 👨‍💻 Author

Divyansh Singh

### 🚀 LeetCode Journey
Documenting SQL and DSA learning on GitHub.
