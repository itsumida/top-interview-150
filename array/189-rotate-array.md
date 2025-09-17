# Question
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

# Solution 
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        n = len(nums)
        if n == 0:
            return None
        k%=n

        nums.reverse()
        nums[:k] = reversed(nums[:k])
        nums[k:] = reversed(nums[k:])

# Approach
"Reverse Trick" 
1. Reverse whole array
2. Then reverse the first k elements
3. Then reverse after k elements
