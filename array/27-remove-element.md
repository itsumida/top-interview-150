# LeetCode 27: Remove Element

## Problem
Remove all occurences of "val" in-place in nums and return the new length of nums

---

## Approach
We can iterate through each i in range(len(nums)) and if nums[i] != val, increment k, which is the new length of nums.  

---

## Code (Python)
```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        k = 0 #new length
        for i in range(len(nums)):
            if nums[i] != val:
                nums[k] = nums[i]
                k+=1
        return k
