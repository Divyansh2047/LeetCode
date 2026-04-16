# Invalid Tweets

## 🧩 Problem Statement

Given a table **Tweets**:

| Column Name | Type |
|------------|------|
| tweet_id | int |
| content | varchar |

- `tweet_id` is the primary key.
- `content` contains the text of the tweet.

### 🎯 Task

A tweet is considered **invalid** if:

- The number of characters in `content` is **greater than 15**

Return the IDs of such tweets.

---

## 📊 Example

### Input

| tweet_id | content |
|----------|-----------------------------------|
| 1 | Let us Code |
| 2 | More than fifteen chars are here! |

### Output

| tweet_id |
|----------|
| 2 |

### Explanation

- Tweet 1 → length = 11 → Valid ✅  
- Tweet 2 → length = 33 → Invalid ❌  

---

## 🧠 Intuition

We need to find tweets whose content length exceeds 15 characters.

So we calculate the length of `content` and filter those greater than 15.

---

## ⚙️ Approach

### Step 1
Select `tweet_id` from the Tweets table

### Step 2
Use:

```
LEN(content)
```

to calculate length

### Step 3
Filter rows where:

```
LEN(content) > 15
```

### Step 4
Return the result

---

## 🛠️ Method Used

### 1️⃣ LEN Function

Calculates the number of characters in a string.

---

### 2️⃣ WHERE Clause

Filters rows based on condition.

---

## 💻 SQL Solution

```sql
SELECT tweet_id 
FROM Tweets 
WHERE LEN(content) > 15;
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We scan all rows in the Tweets table once

---

### Space Complexity

O(1)

- No extra memory used

---

## 🧪 Dry Run

Tweets:

```
1 → "Let us Code" → length = 11 → Valid ✅
2 → "More than fifteen chars are here!" → length = 33 → Invalid ❌
```

Result:

```
2
```

---

## 📚 Learning

- LEN() function is used to calculate string length
- WHERE clause filters rows
- Useful for validation problems in SQL
- Common beginner SQL pattern

---

## 🏁 Final Output

| tweet_id |
|----------|
| 2 |

---

## 🔗 Related Concepts

- SQL SELECT
- WHERE clause
- String functions
- Data validation

---

## 👨‍💻 Author

Divyansh Singh
