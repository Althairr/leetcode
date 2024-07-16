```python
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        # initialize the majority candidate and a counter
        init_value = nums[0]
        counter = 1

        # iterate over the array starting from the second element
        for value in nums[1:]:
            if counter == 0:
                init_value = value
                counter = 1
            elif init_value == value:
                counter += 1
            else:
                counter -= 1
        
        return init_value
```
