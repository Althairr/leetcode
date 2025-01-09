```python
class Solution:
    def prefixCount(self, words: List[str], pref: str) -> int:
        # Variable for storing the result
        result = 0

        # Check if the word starts with the prefix
        for prefix in words:
            if prefix.startswith(pref):
                result += 1
        
        return result
