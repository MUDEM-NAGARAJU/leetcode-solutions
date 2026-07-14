# 🚀 LeetCode 607 | Sales Person | MySQL

## Problem

Find the names of all salespersons who did not have any orders related to the company **"RED"**.

## Intuition

For each salesperson, check whether there exists an order placed with the company named **"RED"**. If no such order exists, include that salesperson in the result.

## Approach

1. Iterate through each salesperson.
2. Use a correlated subquery with `NOT EXISTS`.
3. Join the `Orders` and `Company` tables using `com_id`.
4. Filter rows where the company name is `"RED"`.
5. If no matching order exists for the current salesperson, return their name.

## Complexity

- **Time Complexity:** O(S × O) (worst case)
- **Space Complexity:** O(1)

## Code

```mysql
SELECT s.name
FROM SalesPerson s
WHERE NOT EXISTS (
    SELECT 1
    FROM Orders o
    INNER JOIN Company c
        ON o.com_id = c.com_id
    WHERE o.sales_id = s.sales_id
      AND c.name = 'RED'
);
```
