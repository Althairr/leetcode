```python
class Solution(object):
    def mergeAlternately(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: str
        """
        i = 0 # a pointer to track the words
        result = [] # store the result

        while i < len(word1) or i < len(word2):
            # insert the word into the list
            if i < len(word1):
                result.append(word1[i])
            if i < len(word2):
                result.append(word2[i])
            
            # increment the i 
            i+=1
        return ''.join(result)
        
