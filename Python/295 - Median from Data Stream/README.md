# 🚀 LeetCode 295 | Find Median from Data Stream | Python

## 🔗 Problem Link

https://leetcode.com/problems/find-median-from-data-stream/

- **Difficulty:** Hard
- **Language:** Python

## 🧠 Intuition

The goal is to design a data structure that supports adding numbers from a data stream and efficiently finding the median at any time.

A simple approach is to store all incoming numbers in a list. Whenever a new number is added, sort the list so that the elements remain in ascending order. Since the list is always sorted, the median can be found directly by accessing the middle element(s).

## 🚀 Approach

1. Initialize an empty list to store all numbers.
2. For each `addNum(num)` call:
   - Add the new number to the list.
   - Sort the list to maintain ascending order.
3. For `findMedian()`:
   - Calculate the length of the list.
   - Find the middle index.
   - If the number of elements is odd, return the middle element.
   - Otherwise, return the average of the two middle elements.

## ⏱️ Complexity

- **Time Complexity:**
  - `addNum()` → **O(n log n)**
  - `findMedian()` → **O(1)**

- **Space Complexity:** **O(n)**

where **n** is the number of elements stored in the data stream.

## 💻 Code

```python
class MedianFinder:

    def __init__(self, nums=None):

        if nums == None:
            self.nums = []

    def addNum(self, num: int) -> None:

        self.nums.extend([num])

        self.nums.sort()

    def findMedian(self) -> float:

        length = len(self.nums)

        mid_index = length // 2

        return self.nums[mid_index] if length % 2 else (self.nums[mid_index] + self.nums[mid_index - 1]) / 2


# Your MedianFinder object will be instantiated and called as such:
# obj = MedianFinder()
# obj.addNum(num)
# param_2 = obj.findMedian()
```

## 🏷️ Tags

- Heap (Priority Queue)
- Design
- Data Stream
- Sorting

## ✅ Key Concepts

- Data Structure Design
- Sorting After Each Insertion
- Median Calculation
- Array/List Manipulation
