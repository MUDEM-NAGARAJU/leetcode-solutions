# 🚕 LeetCode 1407 — Top Travellers | SQL

## 🔗 Problem

**LeetCode:** [1407. Top Travellers](https://leetcode.com/problems/top-travellers/)  
**Difficulty:** Easy  
**Language:** MySQL

---

## 🧠 Intuition

The goal is to calculate the total distance travelled by each user.

Some users may not have taken any rides, so we use a `LEFT JOIN` to ensure that every user appears in the result.

For users without rides, `SUM(r.distance)` returns `NULL`.  
We use `COALESCE()` to convert `NULL` into `0`.

Finally, we sort the result by travelled distance in descending order and then by user name alphabetically.

---

## 🚀 Approach

1. Start with the `Users` table so that all users are included.
2. Use `LEFT JOIN` with the `Rides` table using `user_id`.
3. Calculate the total travelled distance using `SUM()`.
4. Use `COALESCE()` to replace `NULL` with `0`.
5. Group the results by `user_id` and `name`.
6. Sort by travelled distance in descending order.
7. If two users have the same distance, sort them by name alphabetically.

---

## 💻 SQL Solution

```mysql
SELECT 
    u.name,
    COALESCE(SUM(r.distance), 0) AS travelled_distance
FROM Users u
LEFT JOIN Rides r 
    ON u.id = r.user_id
GROUP BY u.name, u.id
ORDER BY travelled_distance DESC, u.name;
