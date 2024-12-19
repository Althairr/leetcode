```python
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        # Create a dictionary (hash map) to count the frequency of each character in the magazine
        helper_hash = {}
        
        # Iterate through each character in the magazine
        for char in magazine:
            # Update the count of the character in the hash map
            # If the character doesn't exist in the map, use 0 as the default value
            helper_hash[char] = 1 + helper_hash.get(char, 0)
        
        # Iterate through each character in the ransom note
        for char in ransomNote:
            # Check if the character is not in the hash map or if its count is 0
            if char not in helper_hash or helper_hash[char] <= 0:
                return False  # If so, we cannot construct the ransom note
            # Decrease the count of the character in the hash map
            helper_hash[char] -= 1

        # If we successfully check all characters in the ransom note, return True
        return True
