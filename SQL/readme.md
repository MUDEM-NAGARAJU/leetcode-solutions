# 🚀 LeetCode 1084 | Sales Analysis III | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/sales-analysis-iii/

- **Difficulty:** Easy
- **Language:** MySQL

## 🧠 Intuition

We need to find products that were sold only within the period from `2019-01-01` to `2019-03-30`.

A product must have at least one sale inside the given date range and must not have any sale outside that range.

## ⚡ Approach

1. Find products that have at least one sale between `2019-01-01` and `2019-03-30`.
2. Exclude products that have any sale outside this date range.
3. Use `DISTINCT` to avoid duplicate products.
4. Return the `product_id` and `product_name`.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT DISTINCT
    product_id,
    product_name
FROM Product
WHERE product_id IN (
    SELECT product_id
    FROM Sales
    WHERE sale_date BETWEEN '2019-01-01' AND '2019-03-30'
)
AND product_id NOT IN (
    SELECT product_id
    FROM Sales
    WHERE sale_date NOT BETWEEN '2019-01-01' AND '2019-03-30'
);
```

## ✅ Key Takeaways

- `BETWEEN` filters sales within the required date range.
- `NOT IN` excludes products sold outside the required period.
- `DISTINCT` ensures each product appears only once.
