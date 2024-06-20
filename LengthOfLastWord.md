```python
class Solution(object):
    def lengthOfLastWord(self, s):
        """
        :type s: str
        :rtype: int
        """
        # ensure that the input doesnt have any leading, and trailing whitespaces
        prompt = s.strip()

        # split the input to get the last word
        prompt = prompt.split()

        # ensure there is a words after that
        if not prompt:
            return 0
        
        # track the length of the last word
        n = len(prompt[-1])

        return n
```
