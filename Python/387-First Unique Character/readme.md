# 🔥 LeetCode 387 | First Unique Character in a String 🚀

## 🔗 Problem

**LeetCode:** [387. First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)  
**Difficulty:** Easy  
**Language:** Python

---

## 🧠 Intuition

The goal is to find the index of the first character that appears only once in the string.

We use a dictionary to store:

- The number of times each character appears.
- The latest index of that character.

After building the dictionary, we iterate through it in insertion order and find the first character whose frequency is `1`.

If no unique character exists, we return `-1`.

---

## 🚀 Approach

1. Create an empty dictionary `d`.
2. Traverse the string character by character.
3. If the character already exists in the dictionary:
   - Increment its frequency.
   - Update its index.
4. Otherwise, store its frequency and index.
5. Traverse the dictionary again.
6. Return the index of the first character whose frequency is `1`.
7. If no unique character is found, return `-1`.

---

## ⏱️ Complexity

- **Time Complexity:** O(n)

- **Space Complexity:** O(k)

Where:
- `n` = length of the string
- `k` = number of distinct characters

---

## 💻 Code

```python
class Solution:
    def firstUniqChar(self, s: str) -> int:

        d = {}

        for i in range(len(s)):

            if s[i] in d:
                d[s[i]] = [d[s[i]][0] + 1, i]

            else:
                d[s[i]] = [0, i]

        for i in d:

            if d[i][0] == 0:
                return d[i][1]

        else:
            return -1
