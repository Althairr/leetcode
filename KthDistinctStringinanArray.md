```python
class Solution(object):
    def kthDistinct(self, arr, k):
        """
        :type arr: List[str]
        :type k: int
        :rtype: str
        """
        # initialzie variable to count the occurence of each element in arr
        count = {}

        # variable to track the distinct element
        distinct_count = 0 
        
        for item in arr:
            # iterate every item if its not distinct
            if item in count:
                count[item] += 1 # not distinct element
            else:
                count[item] = 1 # distinct element
        
        # collect the distinct element
        for item in arr:
            if count[item] == 1:
                distinct_count += 1
                if distinct_count == k:
                    return item
        
        # if k-th distinct element does not exist, return ""
        return ""
```
