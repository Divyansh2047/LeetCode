# Count Unique Subjects Taught by Each Teacher

## 🧩 Problem Statement

Given a table **Teacher**:

| Column Name | Type |
|------------|------|
| teacher_id | int  |
| subject_id | int  |
| dept_id    | int  |

- (subject_id, dept_id) is the primary key.
- Each row shows that a teacher teaches a subject in a department.

### 🎯 Task

Calculate the number of **unique subjects** each teacher teaches.

Return the result in any order.

---

## 📊 Example

### Input

| teacher_id | subject_id | dept_id |
|-----------|------------|--------|
| 1 | 2 | 3 |
| 1 | 2 | 4 |
| 1 | 3 | 3 |
| 2 | 1 | 1 |
| 2 | 2 | 1 |
| 2 | 3 | 1 |
| 2 | 4 | 1 |

### Output

| teacher_id | cnt |
|-----------|-----|
| 1 | 2 |
| 2 | 4 |

---

## 🧠 Intuition

A teacher can teach the same subject in multiple departments.

Example:

Teacher 1 teaches:

- Subject 2 in dept 3
- Subject 2 in dept 4
- Subject 3 in dept 3

Here subject **2 appears twice**, but we count it **only once**.

So we need:

> Count unique subject_id for each teacher_id

---

## ⚙️ Approach

### Step 1
Group the table by `teacher_id`

### Step 2
Count unique `subject_id`

### Step 3
Return teacher_id and count

We use:

- `GROUP BY`
- `COUNT(DISTINCT subject_id)`

---

## 🛠️ Method Used

### 1️⃣ GROUP BY

Groups rows based on teacher_id.

Example:

```
Teacher 1 → all rows together
Teacher 2 → all rows together
```

---

### 2️⃣ COUNT DISTINCT

Removes duplicate subjects.

```
Subject 2 in dept 3
Subject 2 in dept 4

Count = 1
```

---

## 💻 SQL Solution

```sql
SELECT 
    teacher_id,
    COUNT(DISTINCT subject_id) AS cnt
FROM Teacher
GROUP BY teacher_id;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in Teacher table once
- GROUP BY and COUNT run in linear time

---

### Space Complexity

O(1)

- No extra memory used
- Only aggregation

---

## 🧪 Dry Run

### Teacher 1

Subjects:

```
2
2
3
```

Unique:

```
2, 3
```

Count = **2**

---

### Teacher 2

Subjects:

```
1
2
3
4
```

Unique:

```
1, 2, 3, 4
```

Count = **4**

---

## 📚 Learning

- GROUP BY is used for aggregation
- COUNT(DISTINCT) removes duplicates
- Useful for SQL interview questions
- Common in data analysis queries

---

## 🏁 Final Output

| teacher_id | cnt |
|-----------|-----|
| 1 | 2 |
| 2 | 4 |

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
Documenting daily LeetCode and SQL learning on GitHub.
