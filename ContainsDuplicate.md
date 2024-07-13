```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        # sort the 'nums'
        nums.sort()

        # because now it is sorted, just check if the next item have same value or not
        for i in range(0, len(nums)-1):
            if (nums[i] == nums [i+1]):
                # returns true if there are any items that have the same value 
                return True
        
        # else return false
        return False
```
