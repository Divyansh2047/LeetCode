# Maximum Subarray

## 🧩 Problem Statement

Given an integer array `nums`, find the **contiguous subarray** (containing at least one number) which has the **largest sum**, and return its sum.

---

## 📊 Example

### Input

```
nums = [-2,1,-3,4,-1,2,1,-5,4]
```

### Output

```
6
```

### Explanation

The subarray:

```
[4, -1, 2, 1]
```

has the largest sum = **6**

---

## 🧠 Intuition

If the current sum becomes negative, it will reduce the sum of any future subarray.

So instead of carrying a negative sum forward, we reset it to zero and start fresh.

This is the core idea of **Kadane’s Algorithm**.

---

## ⚙️ Approach

### Step 1
Initialize:

```
maxSum = -∞
currSum = 0
```

### Step 2
Traverse the array

### Step 3
Add each element:

```
currSum += nums[i]
```

### Step 4
Update maximum:

```
maxSum = max(maxSum, currSum)
```

### Step 5
If current sum becomes negative:

```
currSum = 0
```

---

## 🛠️ Method Used

### 1️⃣ Kadane’s Algorithm

- Efficient way to find maximum subarray sum
- Ignores negative cumulative sums
- Works in linear time

---

## 💻 C++ Solution

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxSum = INT_MIN, currSum = 0;
        for(int i : nums){
            currSum += i;
            maxSum = max(maxSum, currSum);

            if(currSum < 0){
                currSum = 0;
            }
        }
        return maxSum;
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

```
nums = [-2,1,-3,4,-1,2,1,-5,4]
```

Step-by-step:

```
currSum: -2 → reset to 0
currSum: 1
currSum: -2 → reset
currSum: 4
currSum: 3
currSum: 5
currSum: 6 → max
currSum: 1
currSum: 5
```

Maximum = **6**

---

## 📚 Learning

- Kadane’s Algorithm is a classic problem-solving technique
- Helps optimize from O(n²) to O(n)
- Important for interviews
- Works well with dynamic programming concepts

---

## 🏁 Final Output

```
6
```

---

## 🔗 Related Concepts

- Arrays
- Dynamic Programming
- Greedy Algorithms
- Kadane’s Algorithm

---

## 👨‍💻 Author

Divyansh Singh
