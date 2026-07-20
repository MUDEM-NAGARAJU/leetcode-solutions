# 🚀 LeetCode 610 | Triangle Judgement | Simple IF() MySQL Solution

## 🔗 Problem Link

https://leetcode.com/problems/triangle-judgement/

- **Difficulty:** Easy
- **Language:** MySQL

# Intuition

A triangle is valid only if the sum of any two sides is greater than the remaining side. We can directly check these three conditions using the `IF()` function and return `"Yes"` or `"No"` accordingly.

# Approach

- Select all rows from the `Triangle` table.
- Use the `IF()` function to verify:
  - `x + y > z`
  - `y + z > x`
  - `z + x > y`
- Return `"Yes"` if all conditions are true; otherwise, return `"No"`.

# Complexity

- **Time complexity:** `O(n)`

- **Space complexity:** `O(1)`

# Code

```mysql
SELECT *,
       IF(
           x + y > z
           AND y + z > x
           AND z + x > y,
           'Yes',
           'No'
       ) AS triangle
FROM Triangle;
```

## 🏷️ Tags

- SQL
- IF()
- Conditional Logic

## ✅ Key Concepts

- Triangle Inequality
- IF() Function
- Conditional Evaluation
