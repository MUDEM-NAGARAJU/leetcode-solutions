# 🚀 LeetCode 1050 | Actors and Directors Who Cooperated At Least Three Times | MySQL



# Intuition

We need to find actor-director pairs that have worked together at least three times. By grouping records based on both `actor_id` and `director_id`, we can count their collaborations and return only those whose count is greater than or equal to three.

# Approach

- Group the records by `actor_id` and `director_id`.
- Count the number of collaborations using `COUNT(timestamp)`.
- Use the `HAVING` clause to filter groups with at least three collaborations.
- Return the corresponding `actor_id` and `director_id`.

# Complexity

- **Time complexity:** `O(n)`

- **Space complexity:** `O(k)`

Where:
- `n` is the total number of rows in the `ActorDirector` table.
- `k` is the number of unique `(actor_id, director_id)` pairs.

# Code

```mysql
SELECT actor_id,
       director_id
FROM ActorDirector
GROUP BY actor_id, director_id
HAVING COUNT(timestamp) >= 3;
```
