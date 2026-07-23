# Merge Sorted Array

## Intuition

Both `nums1` and `nums2` are already sorted. Instead of merging them and sorting again, we can take advantage of their sorted order. By starting from the end of both arrays, we can place the largest element at the end of `nums1` without overwriting any valid elements.

## Approach

1. Initialize three pointers:
   - `i = m - 1` → Points to the last valid element in `nums1`.
   - `j = n - 1` → Points to the last element in `nums2`.
   - `k = m + n - 1` → Points to the last index of `nums1`.
2. Compare `nums1[i]` and `nums2[j]`.
3. Place the larger element at `nums1[k]`.
4. Move the corresponding pointer backward.
5. Continue until either array is exhausted.
6. If any elements remain in `nums2`, copy them into `nums1`.
7. Since `nums1` is modified in-place, no return value is needed.

## Complexity

- **Time complexity:** `O(m + n)`
- **Space complexity:** `O(1)`

## Code

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
