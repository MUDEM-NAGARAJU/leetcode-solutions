
# 🚀 LeetCode 550 | Game Play Analysis IV | Easy SQL Solution | Beats 95% ⚡

## 🔗 Problem Link

https://leetcode.com/problems/game-play-analysis-iv/

- **Difficulty:** Medium
- **Language:** MySQL

## 🧠 Intuition

We need to find the fraction of players who logged in again exactly one day after their first login.

For each player, we find their first login date. Then we check whether they have a login on the following day.

Finally, we divide the number of players who logged in the next day by the total number of players.

## ⚡ Approach

1. Find the first login date for every player using `MIN(event_date)`.
2. Add one day to the first login date using `DATE_ADD()`.
3. Check whether `(player_id, event_date)` matches the calculated next-day login.
4. Count the distinct players who logged in the next day.
5. Divide by the total number of distinct players.
6. Round the result to two decimal places.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT 
    ROUND(
        COUNT(DISTINCT player_id) /
        (SELECT COUNT(DISTINCT player_id) FROM Activity),
        2
    ) AS fraction
FROM Activity
WHERE (player_id, event_date) IN (
    SELECT 
        player_id,
        DATE_ADD(MIN(event_date), INTERVAL 1 DAY)
    FROM Activity
    GROUP BY player_id
);
