```python
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        # track the length of the lists
        n = len(nums)

        # if the lists is empty, return 0 because there are no elements
        if n == 0:
            return 0

        # initialize a variable to track the the position where  
        # the next unique element (start from index 1) should be placed.
        j = 1

        # loops through all the lists
        for i in range (1, n):
            # check if the current number and the previous one is the same or not
            if nums[i] != nums[i-1]:
                # if the same, place it at the 'j' position
                nums[j] = nums[i]
                j += 1 # increment j to move to the next position
        
        # return the value of the new length of the modified list
        return j
        
```
