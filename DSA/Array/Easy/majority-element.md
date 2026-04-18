# Majority Element

## 🧩 Problem Statement

Given an array of integers `nums` of size `n`, return the **majority element**.

- The majority element is the element that appears **more than ⌊n / 2⌋ times**.
- It is guaranteed that the majority element always exists.

---

## 📊 Example

### Input

```
nums = [3,2,3]
```

### Output

```
3
```

---

### Input

```
nums = [2,2,1,1,1,2,2]
```

### Output

```
2
```

---

## 🧠 Intuition

If an element appears more than half of the time, it will always dominate the array.

We use the **Boyer-Moore Voting Algorithm**:

- If we pair each occurrence of the majority element with a different element, it will still remain at the end.
- So we maintain a candidate and a counter.

---

## ⚙️ Approach

### Step 1
Initialize:

```
freq = 0
ans = 0
```

### Step 2
Traverse the array

### Step 3
If `freq == 0`, choose current element as candidate:

```
ans = nums[i]
```

### Step 4
If current element equals candidate:

```
freq++
```

Else:

```
freq--
```

### Step 5
Return `ans`

---

## 🛠️ Method Used

### 1️⃣ Boyer-Moore Voting Algorithm

- Efficient majority finding technique
- Cancels out different elements
- Leaves the majority element as final candidate

---

## 💻 C++ Solution

```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int freq = 0, ans = 0;
        int s = nums.size();

        for(int i = 0; i < s; i++){
            if(freq == 0){
                ans = nums[i];
            }

            if(ans == nums[i]){
                freq++;
            } else {
                freq--;
            }
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

- No extra memory used

---

## 🧪 Dry Run

Example:

```
nums = [2,2,1,1,1,2,2]
```

Step-by-step:

```
Start → freq=0 → pick 2
2 → freq=1
2 → freq=2
1 → freq=1
1 → freq=0
pick 1 → freq=1
2 → freq=0
pick 2 → freq=1
```

Final answer = **2**

---

## 📚 Learning

- Boyer-Moore is optimal for majority problems
- Works in O(n) time and O(1) space
- Based on cancellation logic
- Common interview question

---

## 🏁 Final Output

```
2
```

---

## 🔗 Related Concepts

- Arrays
- Boyer-Moore Algorithm
- Greedy Techniques
- Optimization

---

## 👨‍💻 Author

Divyansh Singh
