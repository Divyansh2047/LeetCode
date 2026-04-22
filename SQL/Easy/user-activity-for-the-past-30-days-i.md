# User Activity for the Past 30 Days I

## 🧩 Problem Statement

Given a table **Activity**:

| Column Name   | Type |
|--------------|------|
| user_id      | int  |
| session_id   | int  |
| activity_date| date |
| activity_type| enum |

- The table may contain duplicate rows.
- Activity types include:
  - open_session
  - end_session
  - scroll_down
  - send_message

---

### 🎯 Task

Find the **daily active users** for a period of **30 days ending 2019-07-27 (inclusive)**.

- A user is considered active if they perform **at least one activity on a day**
- Return results in any order

---

## 📊 Example

### Input

| user_id | session_id | activity_date | activity_type |
|--------|------------|---------------|---------------|
| 1 | 1 | 2019-07-20 | open_session |
| 1 | 1 | 2019-07-20 | scroll_down |
| 2 | 4 | 2019-07-20 | open_session |
| 2 | 4 | 2019-07-21 | send_message |
| 3 | 2 | 2019-07-21 | open_session |
| 4 | 3 | 2019-06-25 | open_session |

---

### Output

| day | active_users |
|-----|--------------|
| 2019-07-20 | 2 |
| 2019-07-21 | 2 |

---

## 🧠 Intuition

We need to count how many unique users were active on each day.

- A user is active if they perform any activity
- Multiple activities by the same user on the same day should count **once**

So we use:

- Date filtering (last 30 days)
- GROUP BY date
- COUNT DISTINCT user_id

---

## ⚙️ Approach

### Step 1
Filter dates between:

```
2019-06-28 → 2019-07-27
```

### Step 2
Group by `activity_date`

### Step 3
Count distinct users:

```
COUNT(DISTINCT user_id)
```

### Step 4
Return result as:

```
day, active_users
```

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows based on date range.

---

### 2️⃣ GROUP BY

Groups activities per day.

---

### 3️⃣ COUNT DISTINCT

Ensures each user is counted once per day.

---

## 💻 SQL Solution

```sql
SELECT 
    activity_date AS day, 
    COUNT(DISTINCT user_id) AS active_users 
FROM Activity 
WHERE activity_date BETWEEN '2019-06-28' AND '2019-07-27'
GROUP BY activity_date;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in Activity table

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Example:

```
2019-07-20 → users [1,2] → count = 2
2019-07-21 → users [2,3] → count = 2
```

---

## 📚 Learning

- COUNT DISTINCT avoids duplicate counting
- GROUP BY helps aggregate data per day
- Date filtering is common in analytics problems
- Useful for tracking user engagement

---

## 🏁 Final Output

| day | active_users |
|-----|--------------|
| 2019-07-20 | 2 |
| 2019-07-21 | 2 |

---

## 🔗 Related Concepts

- SQL Aggregation
- GROUP BY
- COUNT DISTINCT
- Date Filtering

---

## 👨‍💻 Author

Divyansh Singh
