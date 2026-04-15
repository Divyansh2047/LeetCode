# #595 Big Countries

## 🧩 Problem Statement

Given a table **World**:

| Column Name | Type |
|------------|------|
| name | varchar |
| continent | varchar |
| area | int |
| population | int |
| gdp | bigint |

- `name` is the primary key.
- Each row contains information about a country.

### 🎯 Task

A country is considered **big** if:

- Area ≥ 3,000,000  
OR  
- Population ≥ 25,000,000  

Return the `name`, `population`, and `area` of such countries.

---

## 📊 Example

### Input

| name | continent | area | population | gdp |
|------|-----------|------|------------|-----|
| Afghanistan | Asia | 652230 | 25500100 | 20343000000 |
| Albania | Europe | 28748 | 2831741 | 12960000000 |
| Algeria | Africa | 2381741 | 37100000 | 188681000000 |
| Andorra | Europe | 468 | 78115 | 3712000000 |
| Angola | Africa | 1246700 | 20609294 | 100990000000 |

### Output

| name | population | area |
|------|------------|------|
| Afghanistan | 25500100 | 652230 |
| Algeria | 37100000 | 2381741 |

---

## 🧠 Intuition

We need to filter countries based on two conditions:

- Large area  
- Large population  

If a country satisfies **at least one**, it is considered big.

So we use an OR condition.

---

## ⚙️ Approach

### Step 1
Select `name`, `population`, and `area`

### Step 2
Apply condition:

```
area >= 3000000
```

### Step 3
Apply condition:

```
population >= 25000000
```

### Step 4
Use OR to combine both conditions

### Step 5
Return the result

SQL concepts used:

- SELECT
- WHERE
- OR condition
- Filtering

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows based on given conditions.

---

### 2️⃣ OR Operator

Includes rows that satisfy at least one condition:

```
Condition 1 OR Condition 2
```

---

## 💻 SQL Solution

```sql
SELECT name, population, area 
FROM World 
WHERE area >= 3000000 
OR population >= 25000000;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the World table once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Countries:

```
Afghanistan → population ≥ 25M → Included ✅
Albania     → small area & population → Excluded ❌
Algeria     → population ≥ 25M → Included ✅
Andorra     → very small → Excluded ❌
Angola      → below both limits → Excluded ❌
```

---

## 📚 Learning

- OR condition helps combine multiple filters
- WHERE clause is used for filtering
- Basic SQL querying technique
- Common beginner-level SQL problem

---

## 🏁 Final Output

| name | population | area |
|------|------------|------|
| Afghanistan | 25500100 | 652230 |
| Algeria | 37100000 | 2381741 |

---

## 🔗 Related Concepts

- SQL SELECT
- WHERE clause
- OR operator
- Filtering data

---

## 👨‍💻 Author

Divyansh Singh
