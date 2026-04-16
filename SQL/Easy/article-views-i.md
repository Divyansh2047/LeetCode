# Article Views I

## 🧩 Problem Statement

Given a table **Views**:

| Column Name | Type |
|------------|------|
| article_id | int |
| author_id | int |
| viewer_id | int |
| view_date | date |

- The table may contain duplicate rows.
- Each row indicates that a viewer viewed an article written by an author.
- If `author_id = viewer_id`, it means the author viewed their own article.

### 🎯 Task

Find all authors who viewed at least one of their own articles.

Return the result sorted by `id` in ascending order.

---

## 📊 Example

### Input

| article_id | author_id | viewer_id | view_date |
|------------|-----------|-----------|------------|
| 1 | 3 | 5 | 2019-08-01 |
| 1 | 3 | 6 | 2019-08-02 |
| 2 | 7 | 7 | 2019-08-01 |
| 2 | 7 | 6 | 2019-08-02 |
| 4 | 7 | 1 | 2019-07-22 |
| 3 | 4 | 4 | 2019-07-21 |
| 3 | 4 | 4 | 2019-07-21 |

### Output

| id |
|----|
| 4 |
| 7 |

---

## 🧠 Intuition

We need to find authors who viewed their own articles.

This happens when:

```
author_id = viewer_id
```

Since the table may contain duplicate rows, we must return unique author IDs.

---

## ⚙️ Approach

### Step 1
Select `author_id` from the Views table

### Step 2
Filter rows where:

```
author_id = viewer_id
```

### Step 3
Use DISTINCT to remove duplicate authors

### Step 4
Rename column as `id`

### Step 5
Sort result in ascending order

---

## 🛠️ Method Used

### 1️⃣ WHERE Clause

Filters rows where:

```
author_id = viewer_id
```

---

### 2️⃣ DISTINCT

Removes duplicate author IDs.

---

### 3️⃣ ORDER BY

Sorts the result in ascending order.

---

## 💻 SQL Solution

```sql
SELECT DISTINCT author_id AS id 
FROM Views 
WHERE viewer_id = author_id
ORDER BY id;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the Views table once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Views:

```
(2, 7, 7) → author = viewer → Included ✅
(3, 4, 4) → author = viewer → Included ✅
Duplicate (3, 4, 4) → Ignored by DISTINCT
```

Result:

```
4
7
```

---

## 📚 Learning

- DISTINCT removes duplicates
- WHERE clause filters rows
- ORDER BY sorts output
- Common SQL pattern for filtering and deduplication

---

## 🏁 Final Output

| id |
|----|
| 4 |
| 7 |

---

## 🔗 Related Concepts

- SQL SELECT
- WHERE clause
- DISTINCT
- ORDER BY
- Filtering data

---

## 👨‍💻 Author

Divyansh Singh
