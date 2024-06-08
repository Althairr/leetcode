# Two Sum Algorithm

## Description
This Python class `Solution` implements the `TwoSum` algorithm, which is used to find two numbers within a list that add up to a given target sum.

## Method
The `TwoSum` method takes two parameters:
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
                    return i, j # if the number found, return the number
        return
```

## Analysis
- First, i use a variable called `n` to track the length of the input (lists) given by user. Later that variable can be used to limit the range that can we use in loop.
- Then, we find the two number who adds up to the `target` by iterate in the lists with variable `i` and `j`. Which variable `i` will track the first number in the array lists and `j` will track the next number in the array lists.
- `for j in range (i+1, n):` will find `j` when `j` is `i + 1` and the limit cant be over variable `n`.
- Lastly, we access the number in array list with `nums[i]` to get the right number in the i-th array. Works the same for `j`.
