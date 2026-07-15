# 🚀 LeetCode 151 | Reverse Words in a String | Python

## 🔗 Problem Link

https://leetcode.com/problems/reverse-words-in-a-string/

- **Difficulty:** Medium
- **Language:** Python

## 🧠 Intuition

The goal is to reverse the order of words while removing any leading, trailing, or extra spaces.

Instead of using Python's built-in `split()` function, we manually traverse the string character by character. We build each word, and whenever a space is encountered, we prepend the completed word to the result. This naturally reverses the word order while ignoring multiple consecutive spaces.

## 🚀 Approach

1. Initialize two empty strings:
   - `cur` to store the current word.
   - `res` to store the final reversed string.
2. Traverse each character in the input string.
3. If the character is a letter or digit, append it to `cur`.
4. When a space is encountered:
   - If `cur` is not empty, prepend it to `res`.
   - Reset `cur`.
5. After the loop, check if the last word exists and prepend it.
6. Remove any leading/trailing spaces using `strip()` and return the result.

## ⏱️ Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

where **n** is the length of the input string.

## 💻 Code

```python
class Solution:
    def reverseWords(self, s: str) -> str:

        # return ' '.join(s.split()[::-1])

        res = ""
        cur = ""

        for i in s:

            if (ord(i) >= 97 and ord(i) <= 122) or \
               (ord(i) >= 65 and ord(i) <= 90) or \
               i in "1234567890":

                cur += i

            elif cur:

                res = " " + cur + res
                cur = ""

        if cur:
            res = cur + res

        return res.strip()
```

## 🏷️ Tags

- String
- Two Pointers
- Simulation

## ✅ Key Concepts

- String Traversal
- Manual Word Extraction
- String Manipulation
- Without Using `split()`
