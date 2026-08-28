

# 🚀 LeetCode 262 | Trips and Users | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/trips-and-users/

- **Difficulty:** Hard
- **Language:** MySQL

## 🧠 Intuition

We need to calculate the cancellation rate for each day while ignoring trips where either the driver or client is banned.

First, we identify all banned users. Then, we filter the trips to include only those where both the driver and client are not banned and the request date is within the required period.

Finally, we calculate the cancellation rate by dividing the number of cancelled trips by the total number of valid trips for each day.

## ⚡ Approach

1. Create a CTE `banned_users` containing all banned user IDs.
2. Filter the `Trips` table to keep only valid trips.
3. Exclude trips where the driver or client is banned.
4. Filter the required date range.
5. Group the valid trips by `request_at`.
6. Count cancelled trips using `SUM(status != 'completed')`.
7. Divide cancelled trips by total trips and round to two decimal places.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
WITH banned_users AS (
    SELECT users_id
    FROM Users
    WHERE banned = 'Yes'
),

x AS (
    SELECT *
    FROM Trips t
    WHERE driver_id NOT IN (SELECT * FROM banned_users)
      AND client_id NOT IN (SELECT * FROM banned_users)
      AND request_at BETWEEN '2013-10-01' AND '2013-10-03'
)

SELECT
    x.request_at AS day,
    ROUND(
        SUM(x.status != 'completed') / COUNT(x.request_at),
        2
    ) AS 'Cancellation Rate'
FROM x
GROUP BY request_at;
