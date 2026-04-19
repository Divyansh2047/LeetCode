# Second Highest Salary

## 🧩 Problem Statement

Given a table **Employee**:

| Column Name | Type |
|------------|------|
| id | int |
| salary | int |

- `id` is the primary key.
- Each row contains the salary of an employee.

### 🎯 Task

Find the **second highest distinct salary**.

- If there is no second highest salary, return **NULL**

---

## 📊 Example

### Input

| id | salary |
|----|--------|
| 1 | 100 |
| 2 | 200 |
| 3 | 300 |

### Output

| SecondHighestSalary |
|---------------------|
| 200 |

---

### Input

| id | salary |
|----|--------|
| 1 | 100 |

### Output

| SecondHighestSalary |
|---------------------|
| NULL |

---

## 🧠 Intuition

To find the second highest salary:

- First, find the maximum salary.
- Then remove it from the dataset.
- The maximum of the remaining values will be the second highest.

If no value remains, result will be NULL.

---

## ⚙️ Approach

### Step 1
Find the maximum salary:

```
SELECT MAX(salary) FROM Employee
```

### Step 2
Exclude this maximum salary

### Step 3
Find the maximum from remaining salaries

### Step 4
Return result as `SecondHighestSalary`

---

## 🛠️ Method Used

### 1️⃣ Subquery

Used to find the highest salary.

---

### 2️⃣ MAX Function

Finds the highest value from a column.

---

## 💻 SQL Solution

```sql
SELECT MAX(salary) AS SecondHighestSalary
FROM Employee
WHERE salary < (SELECT MAX(salary) FROM Employee);
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- Table is scanned for MAX operations

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Example:

```
Salaries = [100, 200, 300]
```

Step 1:

```
Max = 300
```

Step 2:

```
Remaining = [100, 200]
```

Step 3:

```
Max = 200
```

---

## 📚 Learning

- Subqueries help solve nested problems
- MAX function is useful for ranking problems
- Common SQL interview question
- Helps understand filtering with aggregation

---

## 🏁 Final Output

| SecondHighestSalary |
|---------------------|
| 200 |

---

## 🔗 Related Concepts

- SQL Subqueries
- Aggregation Functions
- MAX Function
- Filtering Data

---

## 👨‍💻 Author

Divyansh Singh
