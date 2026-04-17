# #136 Single Number

## 🧩 Problem Statement

Given a non-empty array of integers `nums`:

- Every element appears **twice**
- Except for **one element**, which appears only once

### 🎯 Task

Find the element that appears only once.

### Constraints

- Linear time complexity required → **O(n)**
- Constant space complexity required → **O(1)**

---

## 📊 Example

### Input

```
nums = [2,2,1]
```

### Output

```
1
```

---

### Input

```
nums = [4,1,2,1,2]
```

### Output

```
4
```

---

## 🧠 Intuition

XOR is the key here.

Properties of XOR:

```
a ^ a = 0
a ^ 0 = a
```

So:
- Duplicate numbers cancel out
- Only the unique number remains

---

## ⚙️ Approach

### Step 1
Initialize a variable:

```
ans = 0
```

### Step 2
Traverse the array

### Step 3
Apply XOR:

```
ans = ans ^ element
```

### Step 4
Return `ans`

---

## 🛠️ Method Used

### 1️⃣ Bit Manipulation (XOR)

- Cancels duplicate elements
- Leaves only the unique element

---

## 💻 C++ Solution

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int ans = 0;
        for(int i : nums){
            ans ^= i;
        }
        return ans;
    }
};
```

---

## ⏱️ Complexity Analysis

### Time Complexity

O(n)

- We traverse the array once

---

### Space Complexity

O(1)

- No extra memory is used

---

## 🧪 Dry Run

Example:

```
nums = [4,1,2,1,2]
```

Step-by-step:

```
ans = 0
ans ^ 4 = 4
ans ^ 1 = 5
ans ^ 2 = 7
ans ^ 1 = 6
ans ^ 2 = 4
```

Final answer = **4**

---

## 📚 Learning

- XOR is powerful for eliminating duplicates
- Useful in bit manipulation problems
- Helps achieve O(1) space complexity
- Common interview question

---

## 🏁 Final Output

```
4
```

---

## 🔗 Related Concepts

- Bit Manipulation
- XOR Operation
- Arrays
- Optimization Techniques

---

## 👨‍💻 Author

Divyansh Singh
