```python
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        # using two pointer/sliding window
        
        substr_seen = {} # variable to store the substring while iterated  
        i = 0 # left/first pointer, start at s[0]
        max_length = 0 # track the length of the substring
        
        # iterate through the string, by j being the second/right pointer
        for j in range(len(s)):
            char = s[j]

            # if character has been seen/repeated, 
            # update the left pointer
            if char in substr_seen and substr_seen[char] >= i:
                i = substr_seen[char] + 1
            else:
                # update maximum length of substring
                max_length = max(max_length, j - i + 1)
            
            # update last seen index of character
            substr_seen[char] = j  

        # return maximum length found
        return max_length
```
