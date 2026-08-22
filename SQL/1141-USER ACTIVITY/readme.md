

```markdown
# 🚀 LeetCode 1141 | User Activity for the Past 30 Days I | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/user-activity-for-the-past-30-days-i/

- **Difficulty:** Easy
- **Language:** MySQL

## 🧠 Intuition

We need to find the number of unique active users for each day within the given 30-day period.

A user may perform multiple activities on the same day, so we need to count each user only once per day using `COUNT(DISTINCT user_id)`.

## ⚡ Approach

1. Filter the records between `2019-06-28` and `2019-07-28`.
2. Group the records by `activity_date`.
3. Count the distinct users for each day.
4. Return the date as `day` and the count as `active_users`.

## 📊 Complexity

- **Time complexity:** `O(n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT 
    activity_date AS day,
    COUNT(DISTINCT user_id) AS active_users
FROM Activity
WHERE activity_date BETWEEN "2019-06-28" AND "2019-07-28"
GROUP BY activity_date;
