# LeetCode 88: Merge Sorted Array

## Problem
Given two non-decreasing integer arrays with m and n representing valid elements in both of them, respectively.  How to merge array 1 and array 2 when array 1 consists of m + n elements where n is just zeros.  


---

## Approach
I will start to fill the elements from the last end of nums1 by comparing valid elements of nums1 and nums2 one at a time. For this, I'll use three new variables: 
1. last1 = last valid element of nums1
2. last2 = last valid element of nums2
3. lastIndex = last Index of nums1 to overwrite
---

## Code (Python)
```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None: 
          last1 = m - 1
          last2 = n - 1
          lastIndex = m + n - 1

          while last1 >=0 and last2 >= 0:
              if nums1[last1] > nums2[last2]:
                   nums1[lastIndex] = nums1[last1] 
                   last1 -= 1
              else:
                   nums1[lastIndex] = nums2[last2]
                   last2 -= 1
              lastIndex -= 1

         while last2 >= 0:
            nums1[lastIndex] = nums2[last2]
            last2 -= 1
            lastIndex -= 1
    
        
