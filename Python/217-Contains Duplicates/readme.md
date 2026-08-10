# 🚀 LeetCode 217 | Contains Duplicate | Python 💯

## 🔗 Problem

**LeetCode:** [217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)  
**Difficulty:** Easy  
**Language:** Python

---

## 🧠 Intuition

A `set` stores only unique elements.

If the length of the set is different from the length of the original list, it means that duplicate elements exist.

Therefore:

- Same length → No duplicates
- Different length → Duplicates exist

---

## 🚀 Approach

1. Convert the list into a set.
2. Compare the length of the set with the length of the original list.
3. If both lengths are different, return `True`.
4. Otherwise, return `False`.

---

## 💻 Code

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:

        return len(set(nums)) != len(nums)
