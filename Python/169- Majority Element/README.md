# 🚀 LeetCode 169 | Majority Element | Python

## 🔗 Problem Link

https://leetcode.com/problems/majority-element/

- **Difficulty:** Easy
- **Language:** Python

## 🧠 Intuition

Since the majority element appears more than **⌊n / 2⌋** times, counting the frequency of each element allows us to identify it easily. We use a hash map (dictionary) to store the occurrence count of each element while simultaneously tracking the element with the highest frequency.

## 🚀 Approach

1. Initialize an empty dictionary to store the frequency of each element.
2. Create a variable to keep track of the current majority element and its frequency.
3. Traverse the array:
   - Increment the frequency of the current element in the dictionary.
   - If its frequency becomes greater than the current highest frequency, update the majority element.
4. Return the element with the highest frequency.

## ⏱️ Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

where **n** is the length of the input array.

## 💻 Code

```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:

        freq_dict = {}
        highest = [0, 0]

        for i in nums:
            freq_dict[i] = freq_dict.get(i, 0) + 1
            highest = [i, freq_dict[i]] if freq_dict[i] > highest[1] else highest

        return highest[0]
```

## 🏷️ Tags

- Array
- Hash Table
- Counting

## ✅ Key Concepts

- Frequency Counting
- Hash Map (Dictionary)
- Single Pass Traversal
- Tracking Maximum Frequency
