```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        # A dict for storing the number and its last index
        seen_number = {}

        # Traverse all elements in the list nums
        for i in range(len(nums)):
            # Return true if the number is already been seen and the distance is <= k
            if nums[i] in seen_number and abs(i -  seen_number[nums[i]]) <= k:
                return True

            # Update the dictionary with the current number and its index
            seen_number[nums[i]] = i
        
        # If no nearby duplicates are found, return False
        return False
