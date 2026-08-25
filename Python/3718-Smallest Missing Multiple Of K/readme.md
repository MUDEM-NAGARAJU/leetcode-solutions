
# 🚀 LeetCode 3718 | Smallest Missing Multiple of K | Python

## 🔗 Problem Link

https://leetcode.com/problems/smallest-missing-multiple-of-k/

- **Difficulty:** Easy
- **Language:** Python

## 🧠 Intuition

We need to find the smallest positive multiple of `k` that does not exist in `nums`.

To make the lookup efficient, we convert `nums` into a set. Then we check the multiples of `k` one by one until we find the first missing value.

## ⚡ Approach

1. Convert `nums` into a set for fast lookup.
2. Start with the first positive multiple of `k`, which is `k`.
3. Check whether each multiple of `k` exists in the set.
4. If the multiple is not present, return it.
5. Otherwise, move to the next multiple.

## 📊 Complexity

- **Time complexity:** `O(n + m)`
- **Space complexity:** `O(n)`

Where `n` is the number of elements in `nums` and `m` is the number of multiples checked.

## 💻 Code

```python
class Solution(object):
    def missingMultiple(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """

        nums = set(nums)
        n = 1

        while True:
            if (k * n) not in nums:
                return k * n

            n += 1
