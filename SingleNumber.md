```python
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        # initiate a variable to track the result
        result = 0

        # looping through every iteration using XOR operation
        for i in range (len(nums)):
            result = result^nums[i]
        
        # after looping, the only result will be the number that appered only once
        return result
```
