```python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        # using vertical scanning
        # define the first word in the list and add to variable
        first_word = strs[0]

        # iterate through the entire first word and track with 'i'
        for i in range(len(first_word)):
            # loops through the entire word in the 'strs' (starts from second word)
            for word in strs[1:]:
                # checking the matching prefix
                if (i == len(word) or word[i] != first_word[i]):
                    return first_word[0:i]
        
        return first_word
```
