```python
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        # If the string is not a concatenation of the another string
        if str1 + str2 != str2 + str1:
            return "" # return empty string
        
        # If they have the same length, just return str1 (the largest one)
        if len(str1) == len(str2):
            return str1

        # Do a recusion but the str1 divided by str2
        if len(str1) > len(str2):
            return self.gcdOfStrings(str1[len(str2):], str2)
        
        # Else str2 must be longer, so do a recursion but the str2 divided by str1
        return self.gcdOfStrings(str1, str2[len(str1):])
