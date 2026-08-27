
# 🚀 LeetCode 180 | Consecutive Numbers | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/consecutive-numbers/

- **Difficulty:** Medium
- **Language:** MySQL

## 🧠 Intuition

We need to find numbers that appear at least three times consecutively in the `Logs` table.

For each number, we can look at the previous row using `LAG()` and the next row using `LEAD()`. If the previous, current, and next values are all equal, then the number appears consecutively three times.

## ⚡ Approach

1. Use `LAG()` to get the previous number.
2. Use `LEAD()` to get the next number.
3. Compare the previous, current, and next numbers.
4. If all three are equal, the number appears consecutively at least three times.
5. Use `DISTINCT` to avoid duplicate results.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT DISTINCT
    num2 AS ConsecutiveNums
FROM (
    SELECT
        LAG(num) OVER() AS num1,
        num AS num2,
        LEAD(num) OVER() AS num3
    FROM Logs
) x
WHERE num1 = num2
AND num2 = num3;
