# Replace Employee ID With The Unique Identifier

## 🧩 Problem Statement

Given two tables:

### Employees

| Column Name | Type |
|------------|------|
| id | int |
| name | varchar |

- `id` is the primary key.

---

### EmployeeUNI

| Column Name | Type |
|------------|------|
| id | int |
| unique_id | int |

- `(id, unique_id)` is the primary key.

---

### 🎯 Task

Show the `unique_id` of each employee.

- If an employee does not have a unique ID, return **NULL**
- Return the result in any order

---

## 📊 Example

### Input

**Employees**

| id | name |
|----|------|
| 1 | Alice |
| 7 | Bob |
| 11 | Meir |
| 90 | Winston |
| 3 | Jonathan |

**EmployeeUNI**

| id | unique_id |
|----|-----------|
| 3 | 1 |
| 11 | 2 |
| 90 | 3 |

---

### Output

| unique_id | name |
|-----------|------|
| null | Alice |
| null | Bob |
| 2 | Meir |
| 3 | Winston |
| 1 | Jonathan |

---

## 🧠 Intuition

We need all employees, even if they don’t have a unique ID.

So we use a **LEFT JOIN**:

- Take all rows from `Employees`
- Match with `EmployeeUNI`
- If no match exists → NULL is returned automatically

---

## ⚙️ Approach

### Step 1
Use `Employees` as the base table

### Step 2
LEFT JOIN with `EmployeeUNI` on `id`

### Step 3
Select:

```
unique_id, name
```

### Step 4
Return result

---

## 🛠️ Method Used

### 1️⃣ LEFT JOIN

- Keeps all rows from left table
- Fills NULL when no match exists

---

### 2️⃣ JOIN Condition

```
e.id = e1.id
```

---

## 💻 SQL Solution

```sql
SELECT e1.unique_id, e.name 
FROM Employees e
LEFT JOIN EmployeeUNI e1
ON e.id = e1.id;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan both tables once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Employees:

```
1 → no match → NULL
7 → no match → NULL
11 → match → 2
90 → match → 3
3 → match → 1
```

---

## 📚 Learning

- LEFT JOIN is used to keep unmatched data
- Useful for handling missing values
- Important SQL concept for interviews
- Helps combine multiple tables

---

## 🏁 Final Output

| unique_id | name |
|-----------|------|
| null | Alice |
| null | Bob |
| 2 | Meir |
| 3 | Winston |
| 1 | Jonathan |

---

## 🔗 Related Concepts

- SQL JOIN
- LEFT JOIN
- NULL handling
- Table relationships

---

## 👨‍💻 Author

Divyansh Singh
