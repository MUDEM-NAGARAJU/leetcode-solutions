# 🚀 LeetCode 3345 | Smallest Divisible Digit Product I | Python

## 🔗 Problem Link

https://leetcode.com/problems/smallest-divisible-digit-product-i/

- **Difficulty:** Easy
- **Language:** Python

---

## 🧠 Intuition

The goal is to find the smallest integer greater than or equal to `n` whose product of digits is divisible by `t`.

Since the constraints are small, we can simply iterate through the numbers starting from `n`, compute the product of their digits, and return the first number that satisfies the condition.

---

## ⚡ Approach

1. Start iterating from `n`.
2. For each number:
   - Store it in a temporary variable.
   - Calculate the product of all its digits.
3. Check if the product is divisible by `t`.
4. If it is, return the current number.
5. Since the numbers are checked in increasing order, the first valid number is the smallest possible answer.

---

## 📊 Complexity

- **Time Complexity:** `O(k × d)`
  - `k` = Number of integers checked.
  - `d` = Number of digits in each integer.

- **Space Complexity:** `O(1)`

---

## 💻 Code

```python
class Solution:
    def smallestNumber(self, n: int, t: int) -> int:

        for i in range(n, 101):

            product = 1
            temp = i

            while i != 0:

                product *= (i % 10)
                i //= 10

            if product % t == 0:

                return temp
```

---

## ✅ Key Takeaways

- Simple brute-force solution.
- Computes the product of digits for each candidate number.
- Returns immediately when a valid number is found.
- Uses constant extra space.
