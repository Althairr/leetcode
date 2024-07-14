```python
class Solution(object):
    def isPalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """
        # lowered the string
        s1 = s.lower() 
        
        # ensure that there is no more non-alfanumeric characters
        s2 = ''.join(char for char in s1 if char.isalnum())  
        
        # make 's2' a list so that we can use reverse()
        s2_list = list(s2)  
        s2_list.reverse() 

        # change the list into the string
        reversed_s2 = ''.join(s2_list)  
        
        # compare the string given and the reversed string
        return s2 == reversed_s2  
```
