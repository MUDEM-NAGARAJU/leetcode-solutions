# 🚀 LeetCode 627 | Swap Sex of Employees | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/swap-salary/

* **Difficulty:** Easy
* **Language:** MySQL

## 🧠 Intuition

The task is to swap the values in the `sex` column for every employee:

* `'m'` → `'f'`
* `'f'` → `'m'`

A `CASE` expression allows us to perform this swap in a single `UPDATE` statement without using temporary variables.

## 🚀 Approach

1. Update every row in the `Salary` table.
2. Check the current value of `sex` using `CASE`.
3. Replace `'m'` with `'f'`.
4. Replace `'f'` with `'m'`.

## ⏱️ Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(1)

where `n` is the number of employees.

## 💻 Code

```mysql
UPDATE Salary
SET sex =
    CASE sex
        WHEN 'm' THEN 'f'
        WHEN 'f' THEN 'm'
    END;
```

## 🏷️ Tags

* SQL
* UPDATE
* CASE

## ✅ Key Concepts

* UPDATE statement
* CASE expression
* Conditional data transformation
