```python
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        # initialize variable for indexing the array
        index = 0

        # track the length of the array
        n = len(nums)

        # looping to find the element
        for i in range (n):
            # check if the nums[i] not matched with val
            if (nums[i] != val):
                # increment the index, so that it will iterate the entire nums
                nums[index] = nums[i];
                index += 1
        
        return index
```
