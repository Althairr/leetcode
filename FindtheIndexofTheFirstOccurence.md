```python
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        # if length of the needle is greather than the haystack, 
        # then the needle will not in the haystack
        if len(needle) > len(haystack):
            return -1
        
        # if there is needle in the haystack,
        if needle in haystack:
            # return the index of the first occurrence of needle in the haystack.
            return haystack.index(needle);

        
        # else there is no needle in the haystack
        return -1
```
