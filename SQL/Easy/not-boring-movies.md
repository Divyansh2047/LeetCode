# Not Boring Movies

## 🧩 Problem Statement

Given a table **Cinema**:

| Column Name | Type |
|------------|------|
| id | int |
| movie | varchar |
| description | varchar |
| rating | float |

- `id` is the primary key.
- Each row contains details of a movie.

### 🎯 Task

Find movies that:

- Have an **odd-numbered id**
- Have a **description not equal to "boring"**

Return the result sorted by `rating` in **descending order**.

---

## 📊 Example

### Input

| id | movie | description | rating |
|----|--------|-------------|--------|
| 1 | War | great 3D | 8.9 |
| 2 | Science | fiction | 8.5 |
| 3 | irish | boring | 6.2 |
| 4 | Ice song | Fantacy | 8.6 |
| 5 | House card | Interesting | 9.1 |

### Output

| id | movie | description | rating |
|----|--------|-------------|--------|
| 5 | House card | Interesting | 9.1 |
| 1 | War | great 3D | 8.9 |

---

## 🧠 Intuition

We need to filter movies based on two conditions:

1. ID should be odd  
2. Description should not be "boring"  

Then sort the result based on rating.

---

## ⚙️ Approach

### Step 1
Select all columns from Cinema table

### Step 2
Filter rows where:

```
id % 2 = 1
```

### Step 3
Exclude rows where:

```
description = 'boring'
```

### Step 4
Sort results:

```
ORDER BY rating DESC
```

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows based on conditions.

---

### 2️⃣ Modulus Operator (%)

Used to check odd numbers:

```
id % 2 = 1
```

---

### 3️⃣ ORDER BY

Sorts data in descending order.

---

## 💻 SQL Solution

```sql
SELECT * 
FROM Cinema 
WHERE id % 2 = 1 
AND description != 'boring'
ORDER BY rating DESC;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the Cinema table

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Movies:

```
1 → odd & not boring → Included ✅
3 → odd but boring → Excluded ❌
5 → odd & not boring → Included ✅
```

Sorted by rating:

```
5 (9.1)
1 (8.9)
```

---

## 📚 Learning

- Modulus operator helps identify odd/even numbers
- WHERE clause filters rows
- ORDER BY sorts results
- Combining multiple conditions is common in SQL

---

## 🏁 Final Output

| id | movie | description | rating |
|----|--------|-------------|--------|
| 5 | House card | Interesting | 9.1 |
| 1 | War | great 3D | 8.9 |

---

## 🔗 Related Concepts

- SQL SELECT
- WHERE clause
- Modulus operator
- ORDER BY
- Filtering and sorting

---

## 👨‍💻 Author

Divyansh Singh
