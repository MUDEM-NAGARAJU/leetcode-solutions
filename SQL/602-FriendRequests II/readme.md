
# 🚀 LeetCode 602 | Friend Requests II: Who Has the Most Friends | MySQL

## 🔗 Problem Link

https://leetcode.com/problems/friend-requests-ii-who-has-the-most-friends/

- **Difficulty:** Medium
- **Language:** MySQL

## 🧠 Intuition

Each accepted friend request creates a friendship between two people.

A person can appear either as a `requester_id` or an `accepter_id`, so we combine both columns into a single list of IDs. Then we count how many times each ID appears. The person with the highest count has the most friends.

## ⚡ Approach

1. Select all `requester_id` values and rename them as `id`.
2. Select all `accepter_id` values and rename them as `id`.
3. Use `UNION ALL` to combine both lists without removing duplicates.
4. Group the combined results by `id`.
5. Count the occurrences of each ID.
6. Sort the result by the count in descending order.
7. Return the person with the highest count using `LIMIT 1`.

## 📊 Complexity

- **Time complexity:** `O(n log n)`
- **Space complexity:** `O(n)`

## 💻 Code

```mysql
SELECT 
    id,
    COUNT(*) AS num
FROM (
    SELECT requester_id AS id
    FROM RequestAccepted

    UNION ALL

    SELECT accepter_id AS id
    FROM RequestAccepted
) x
GROUP BY id
ORDER BY num DESC
LIMIT 1;
