# LeetCode 80: Remove Duplicates from a Sorted array

## Problem
We can tolerate repeatedness of numbers just 2 times. Remove the number if it is coming third time. Return the length of the new array.

---

## Approach
We are going to keep the first 2 elements in the array. For the third element, we check if it differs from first element. If it does, we keep the number if not skip to the next one.

---

## Code (Python)
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        k = 0
        for i in range(len(nums)):
            if k < 2:
                nums[k] = nums[i]
                k += 1
            else:
                if nums[i] != nums[k-2]:
                    nums[k] = nums[i]
                    k += 1
        return k
