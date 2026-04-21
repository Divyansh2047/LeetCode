# Project Employees I

## 🧩 Problem Statement

Given two tables:

### Project

| Column Name | Type |
|------------|------|
| project_id | int |
| employee_id | int |

- `(project_id, employee_id)` is the primary key.
- Each row indicates an employee working on a project.

---

### Employee

| Column Name | Type |
|------------|------|
| employee_id | int |
| name | varchar |
| experience_years | int |

- `employee_id` is the primary key.
- Contains experience of each employee.

---

### 🎯 Task

For each project, calculate the **average experience years** of its employees.

- Round the result to **2 decimal places**
- Return the result in any order

---

## 📊 Example

### Input

**Project**

| project_id | employee_id |
|------------|-------------|
| 1 | 1 |
| 1 | 2 |
| 1 | 3 |
| 2 | 1 |
| 2 | 4 |

**Employee**

| employee_id | name | experience_years |
|-------------|------|------------------|
| 1 | Khaled | 3 |
| 2 | Ali | 2 |
| 3 | John | 1 |
| 4 | Doe | 2 |

---

### Output

| project_id | average_years |
|------------|---------------|
| 1 | 2.00 |
| 2 | 2.50 |

---

## 🧠 Intuition

We need to:

- Combine project and employee data
- Get experience of employees per project
- Calculate average for each project

So we use:

- JOIN → to combine tables
- AVG → to compute average
- GROUP BY → per project

---

## ⚙️ Approach

### Step 1
Join `Project` and `Employee` tables using `employee_id`

### Step 2
Group by `project_id`

### Step 3
Calculate:

```
AVG(experience_years)
```

### Step 4
Round result to 2 decimal places

---

## 🛠️ Method Used

### 1️⃣ JOIN

Combines employee experience with project data.

---

### 2️⃣ GROUP BY

Groups employees per project.

---

### 3️⃣ AVG Function

Calculates average experience.

---

### 4️⃣ ROUND Function

Formats result to 2 decimal places.

---

## 💻 SQL Solution

```sql
SELECT p.project_id, 
       ROUND(AVG(e.experience_years * 1.0), 2) AS average_years
FROM Project p
LEFT JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY p.project_id;
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

Project 1:

```
Employees → [3, 2, 1]
Average → (3 + 2 + 1) / 3 = 2.00
```

Project 2:

```
Employees → [3, 2]
Average → (3 + 2) / 2 = 2.50
```

---

## 📚 Learning

- JOIN helps combine multiple tables
- GROUP BY is used for aggregation
- AVG computes averages
- ROUND formats numeric output
- Very common SQL interview pattern

---

## 🏁 Final Output

| project_id | average_years |
|------------|---------------|
| 1 | 2.00 |
| 2 | 2.50 |

---

## 🔗 Related Concepts

- SQL JOIN
- GROUP BY
- AVG Function
- ROUND Function
- Aggregation

---

## 👨‍💻 Author

Divyansh Singh
