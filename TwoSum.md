# twoSum Algorithm

## Description
This Python class `Solution` implements the `twoSum` algorithm, which is used to find two numbers within a list that add up to a given target sum.

## Method
The `twoSum` method takes two parameters:
- `nums`: a list of integers
- `target`: an integer representing the target sum

It returns a list containing the indices of the two numbers within the input list `nums` that add up to the `target` sum.

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        # track the nums
        n = len(nums)

        # looping to find the number within the nums
        for i in range(n-1): # i starts from zero
            for j in range (i+1, n): # j stars with next number, which is i +1
                if (nums[i] + nums[j] == target):
                    return i, j # if the number found, return the number to main
        return

