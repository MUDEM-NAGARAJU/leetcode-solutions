# 🚀 LeetCode 66 | Plus One | Python

## 🔗 Problem Link

https://leetcode.com/problems/plus-one/

- **Difficulty:** Easy
- **Language:** Python

## 🧠 Intuition

The digits represent a non-negative integer. Starting from the last digit, simulate the addition of one.

- If the current digit is less than `9`, simply increment it and return the result.
- If the digit is `9`, it becomes `0` and the carry is propagated to the previous digit.
- If all digits are `9`, insert `1` at the beginning of the array.

## 🚀 Approach

1. Traverse the array from right to left.
2. If the current digit is less than `9`:
   - Increment it by `1`.
   - Return the updated array immediately.
3. Otherwise:
   - Set the current digit to `0`.
   - Continue to the previous digit.
4. If the loop finishes, it means every digit was `9`.
5. Insert `1` at the beginning of the array and return the result.

## ⏱️ Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

where **n** is the number of digits.

## 💻 Code

```python
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:

        for i in range(len(digits) - 1, -1, -1):

            if digits[i] < 9:

                digits[i] += 1
                return digits

            else:

                digits[i] = 0

        digits.insert(0, 1)

        return digits
```

## 🏷️ Tags

- Array
- Math
- Simulation

## ✅ Key Concepts

- Carry Propagation
- Array Traversal
- Simulation
