# 🚀 LeetCode 1068 | Product Sales Analysis I | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/product-sales-analysis-i/

- **Difficulty:** Easy
- **Language:** MySQL

---

## 📝 Problem Statement

Given the `Sales` and `Product` tables, return the `product_name`, `year`, and `price` for each sale.

---

## 🧠 Intuition

The `Sales` table stores the sale details, while the `Product` table stores the product names. Since both tables share the `product_id`, we can join them to retrieve the required information.

---

## ⚡ Approach

1. Join the `Sales` and `Product` tables using `product_id`.
2. Select the required columns:
   - `product_name`
   - `year`
   - `price`
3. Return the result.

---

## 📊 Complexity

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

---

## 💻 MySQL Solution

```mysql
# Write your MySQL query statement below

SELECT
    p.product_name,
    s.year,
    s.price
FROM Sales s
LEFT JOIN Product p
ON s.product_id = p.product_id;
```

---

## ✅ Key Concepts

- SQL JOIN
- LEFT JOIN
- Selecting Specific Columns
- Relational Database Queries

---

### ⭐ If you found this solution helpful, consider giving the repository a star!
