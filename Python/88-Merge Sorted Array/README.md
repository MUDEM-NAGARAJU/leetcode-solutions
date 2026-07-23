# ⚡ LeetCode 88 | Merge Sorted Array | Python

## 🔗 Problem Link

https://leetcode.com/problems/merge-sorted-array/

- **Difficulty:** Easy
- **Language:** Python

## 🧠 Intuition

Both `nums1` and `nums2` are already sorted. Instead of merging the arrays and sorting them again, we can compare elements from the end of both arrays and place the larger element at the last available position in `nums1`. This allows us to merge the arrays in-place without using extra space.

## 🚀 Approach

1. Initialize three pointers:
   - `i = m - 1` → Last valid element in `nums1`.
   - `j = n - 1` → Last element in `nums2`.
   - `k = m + n - 1` → Last position in `nums1`.
2. Compare `nums1[i]` and `nums2[j]`.
3. Place the larger element at `nums1[k]`.
4. Move the corresponding pointer (`i` or `j`) and decrement `k`.
5. Continue until one of the arrays is exhausted.
6. If elements remain in `nums2`, copy them into `nums1`.
7. Since the remaining elements in `nums1` are already in the correct position, no further processing is required.

## ⏱️ Complexity

- **Time Complexity:** O(m + n)
- **Space Complexity:** O(1)

where:
- **m** is the number of valid elements in `nums1`.
- **n** is the number of elements in `nums2`.

## 💻 Code

```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """

        i = m - 1
        j = n - 1
        k = m + n - 1

        while i >= 0 and j >= 0:
            if nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1

        while j >= 0:
            nums1[k] = nums2[j]
            j -= 1
            k -= 1
```

## 🏷️ Tags

- Array
- Two Pointers
- Sorting
- In-Place

## ✅ Key Concepts

- Three-Pointer Technique
- In-Place Array Modification
- Efficient Merging
- Two Pointer Algorithm
- Space Optimization
