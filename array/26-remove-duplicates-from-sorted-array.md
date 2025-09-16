# LeetCode 26: Remove Duplicates from a Sorted Array

## Problem
We have to remove duplicates from an array and return the new length

---

## Approach
We keep element 1 always since it is always unique. Then we check  nums[0] with nums[1]: if they are different we set nums[1]=nums[k] and increase k for the next unique number.  

---

## Code (Python)
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
            k = 1
            for i in range(1, len(nums)):
                if nums[i] != nums[k-1]:
                      nums[k] = nums[i]
                      k += 1
            return k

