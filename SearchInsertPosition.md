```python
class Solution(object):
    def searchInsert(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """

        # initialize variables
        high = len(nums)
        low = 0

        # perform binary search
        while low < high:
            # calculate index in the middle
            mid = (low + high) // 2

            # find the target in the right side
            if nums[mid] < target:
                low = mid + 1
            else:
                # find the target in the left side
                high = mid
        
        # return the index
        return low
```
