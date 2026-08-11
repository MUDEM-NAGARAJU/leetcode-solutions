# 🚀 LeetCode 2996 | Smallest Missing Integer Greater Than Sequential Prefix Sum 🧮

## 🔗 Problem

**LeetCode:** [2996. Smallest Missing Integer Greater Than Sequential Prefix Sum](https://leetcode.com/problems/smallest-missing-integer-greater-than-sequential-prefix-sum/)

**Difficulty:** Easy  
**Language:** Python

---

## 🧠 Intuition

We first find the sum of the longest consecutive prefix starting from the first element.

After calculating this sum, we need to find the smallest integer greater than or equal to this sum that does not exist in the array.

A `set` is used for fast membership checking.

---

## 🚀 Approach

1. Initialize `long_sum` with the first element.
2. Traverse the array from the beginning.
3. Keep adding elements while they form a consecutive sequence.
4. Stop when the consecutive sequence breaks.
5. Convert the array into a set for fast lookups.
6. Start checking from `long_sum`.
7. If the number is not present in the set, return it.
8. Otherwise, increment it and continue searching.

---

## 💻 Code

```python
class Solution:
    def missingInteger(self, nums: List[int]) -> int:

        long_sum = nums[0]

        for i in range(len(nums) - 1):

            if nums[i] == nums[i + 1] - 1:
                long_sum += nums[i + 1]

            else:
                break

        num_set = set(nums)

        while True:

            if long_sum not in num_set:
                return long_sum

            long_sum += 1
