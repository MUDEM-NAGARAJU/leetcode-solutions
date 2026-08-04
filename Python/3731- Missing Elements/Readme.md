# 🚀 LeetCode 3731 | Find Missing Elements | Python

## 🔗 Problem Link

https://leetcode.com/problems/find-missing-elements/

- **Difficulty:** Easy
- **Language:** Python

## 🧠 Intuition

The problem asks us to find every missing integer between the minimum and maximum values of the given array.

A straightforward solution is to iterate through all integers in this range and check whether each number exists in the array. Any number that is absent is added to the result list.

## 🚀 Approach

1. Create an empty list to store missing numbers.
2. Find the minimum and maximum values in the array.
3. Iterate through every integer from `min(nums)` to `max(nums)`.
4. If a number is not present in the array, append it to the result.
5. Return the list of missing numbers.

## ⏱️ Complexity

- **Time Complexity:** **O(n × r)**
- **Space Complexity:** **O(k)**

Where:

- `n` = number of elements in the array.
- `r` = `max(nums) - min(nums)`.
- `k` = number of missing elements returned.

## 💻 Code

```python
class Solution:
    def findMissingElements(self, nums: List[int]) -> List[int]:

        miss = []

        for i in range(min(nums), max(nums)):

            if i not in nums:

                miss.append(i)

        return miss
```

## 🏷️ Tags

- Array
- Brute Force
- Simulation

## ✅ Key Concepts

- Array Traversal
- Range Iteration
- Membership Checking
- Missing Elements
- Brute Force
