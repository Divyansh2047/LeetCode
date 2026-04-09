# #1757 Find Products that are Low Fat and Recyclable

## 🧩 Problem Statement

Given a table **Products**:

| Column Name | Type |
|------------|------|
| product_id | int |
| low_fats | enum |
| recyclable | enum |

- `product_id` is the primary key.
- `low_fats` can be **'Y' or 'N'**
- `recyclable` can be **'Y' or 'N'**

### 🎯 Task

Find the IDs of products that are:

- Low fat
- Recyclable

Return the result in any order.

---

## 📊 Example

### Input

| product_id | low_fats | recyclable |
|------------|----------|------------|
| 0 | Y | N |
| 1 | Y | Y |
| 2 | N | Y |
| 3 | Y | Y |
| 4 | N | N |

### Output

| product_id |
|------------|
| 1 |
| 3 |

### Explanation

Only product **1** and **3** satisfy both conditions:

- Low fat = Y
- Recyclable = Y

---

## 🧠 Intuition

We need to filter products based on two conditions.

A product should be:

```
low_fats = Y
recyclable = Y
```

So we simply filter rows where both conditions are true and return the `product_id`.

---

## ⚙️ Approach

### Step 1
Select `product_id` from Products table

### Step 2
Apply condition:

```
low_fats = 'Y'
```

### Step 3
Apply condition:

```
recyclable = 'Y'
```

### Step 4
Return filtered product_id

SQL concepts used:

- SELECT
- WHERE
- AND condition
- Filtering

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows based on conditions.

Example:

```
low_fats = 'Y'
recyclable = 'Y'
```

Only rows that satisfy both conditions are selected.

---

### 2️⃣ AND Operator

Ensures both conditions are true.

```
Condition 1 AND Condition 2
```

Both must be satisfied.

---

## 💻 SQL Solution

```sql
SELECT product_id 
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y';
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the Products table once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Products table:

```
0 → Y N → Not recyclable ❌
1 → Y Y → Valid ✅
2 → N Y → Not low fat ❌
3 → Y Y → Valid ✅
4 → N N → Invalid ❌
```

Result:

```
1
3
```

---

## 📚 Learning

- WHERE clause is used to filter data
- AND operator combines conditions
- Basic SQL filtering problem
- Useful for beginner SQL understanding

---

## 🏁 Final Output

| product_id |
|------------|
| 1 |
| 3 |

---

## 🔗 Related Concepts

- SQL SELECT
- WHERE clause
- AND operator
- Filtering data
- Basic SQL queries

---

## 👨‍💻 Author

Divyansh Singh

