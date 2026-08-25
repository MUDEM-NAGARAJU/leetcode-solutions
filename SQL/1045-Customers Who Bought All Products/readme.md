
# 🚀 LeetCode 1045 | Customers Who Bought All Products | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/customers-who-bought-all-products/

- **Difficulty:** Medium
- **Language:** MySQL

## 🧠 Intuition

We need to find customers who bought every product available in the `Product` table.

For each customer, we count the number of distinct products they purchased. If this count is equal to the total number of products, then that customer has purchased every product.

## ⚡ Approach

1. Group the `Customer` table by `customer_id`.
2. Count the distinct products purchased by each customer.
3. Find the total number of products in the `Product` table.
4. Use `HAVING` to keep only customers whose distinct product count equals the total product count.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT customer_id
FROM Customer
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key) = (
    SELECT COUNT(product_key)
    FROM Product
);
```

## ✅ Key Takeaways

- `COUNT(DISTINCT product_key)` counts the unique products purchased by each customer.
- The subquery finds the total number of products.
- `HAVING` filters customers who purchased all available products.
