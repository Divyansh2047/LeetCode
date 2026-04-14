# Find Customer Referee

## 🧩 Problem Statement

Given a table **Customer**:

| Column Name | Type |
|------------|------|
| id | int |
| name | varchar |
| referee_id | int |

- `id` is the primary key.
- `referee_id` contains the id of the customer who referred them.
- If `referee_id` is NULL, it means the customer was not referred by anyone.

### 🎯 Task

Find the names of customers who are:

- Not referred by any customer  
OR  
- Referred by a customer whose `id` is **not equal to 2**

Return the result in any order.

---

## 📊 Example

### Input

| id | name | referee_id |
|----|------|------------|
| 1 | Will | null |
| 2 | Jane | null |
| 3 | Alex | 2 |
| 4 | Bill | null |
| 5 | Zack | 1 |
| 6 | Mark | 2 |

### Output

| name |
|------|
| Will |
| Jane |
| Bill |
| Zack |

---

## 🧠 Intuition

We need to filter customers based on their `referee_id`.

There are two valid cases:

1. Customer is **not referred by anyone**  
   → `referee_id IS NULL`

2. Customer is referred by someone **other than id = 2**  
   → `referee_id != 2`

So we combine both conditions.

---

## ⚙️ Approach

### Step 1
Select `name` from the Customer table

### Step 2
Include customers where:

```
referee_id != 2
```

### Step 3
Also include customers where:

```
referee_id IS NULL
```

### Step 4
Return the result

SQL concepts used:

- WHERE clause
- OR condition
- NULL handling

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows based on conditions.

---

### 2️⃣ OR Operator

Allows inclusion of multiple conditions:

```
Condition 1 OR Condition 2
```

---

### 3️⃣ NULL Handling

```
referee_id IS NULL
```

Used to check customers with no referee.

---

## 💻 SQL Solution

```sql
SELECT name 
FROM Customer
WHERE referee_id != 2 
OR referee_id IS NULL;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the Customer table once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Customer table:

```
Will  → NULL → Included ✅
Jane  → NULL → Included ✅
Alex  → 2    → Excluded ❌
Bill  → NULL → Included ✅
Zack  → 1    → Included ✅
Mark  → 2    → Excluded ❌
```

Result:

```
Will
Jane
Bill
Zack
```

---

## 📚 Learning

- Handling NULL values is important in SQL
- OR condition allows multiple filtering cases
- WHERE clause is used for filtering rows
- Common SQL interview pattern

---

## 🏁 Final Output

| name |
|------|
| Will |
| Jane |
| Bill |
| Zack |

---

## 🔗 Related Concepts

- SQL WHERE clause
- NULL handling
- Logical operators (OR)
- Filtering data

---

## 👨‍💻 Author

Divyansh Singh
